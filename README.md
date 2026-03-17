package com.seed.dao;
 
import java.util.List;
 
import com.seed.entity.Orders;
import com.seed.util.JPAUtil;
 
import jakarta.persistence.EntityManager;
import jakarta.persistence.Query;
 
public class OrderDAO {
 
    EntityManager em=JPAUtil.getEntityManager();
    
    //insert
    public void saveOrder(Orders orders)
    {
    	em.getTransaction().begin();
    	
    	em.persist(orders.getCustomer());
    	em.persist(orders);
    	
    	em.getTransaction().commit();
    	
    	System.out.println("data inserted successfully...");	
    }
   
    
    //select all
    public List<Orders> getAllOrders() {
    	
    	Query q=em.createQuery("from Orders");
    	 return q.getResultList();
    }
    
    //select by product
    
    public List<Orders> getOrdersByProduct(String product) {
    	
    	Query q=em.createQuery("SELECT o from Orders o WHERE o.product=:p");
    	
    	   q.setParameter("p", product);
    	 return q.getResultList();
    }
    
    //update
    public void updateOrder(int id,double price)
    {
    	em.getTransaction().begin();
    	
    	Orders o=em.find(Orders.class, id);
    	  o.setPrice(price);
    	
    	em.getTransaction().commit();
    	
    	System.out.println("data updated successfully...");	
    }
    
    //delete
    public void deleteOrder(int id,double price)
    {
    	em.getTransaction().begin();
    	
    	Orders o=em.find(Orders.class, id);
    	  em.remove(o);
    	
    	em.getTransaction().commit();
    	
    	System.out.println("data deleted successfully...");	
    }
    
    
    
    
}
 
