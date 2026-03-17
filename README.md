package com.seed;

import java.util.List;

import com.seed.dao.OrderDAO;
import com.seed.entity.Customer;
import com.seed.entity.Orders;

public class App {

    public static void main(String[] args) {

        Customer c1 = new Customer();
        c1.setCustomerId(3);
        c1.setName("Prachi");
        c1.setEmail("prachi@gmail.com");

        Orders o1 = new Orders();
        o1.setOrderId(105);
        o1.setProduct("Books");
        o1.setPrice(1000);
        o1.setCustomer(c1);

        Orders o2 = new Orders();
        o2.setOrderId(106);
        o2.setProduct("Clothes");
        o2.setPrice(5000);
        o2.setCustomer(c1);

        OrderDAO dao = new OrderDAO();

        dao.saveOrder(o1);
        dao.saveOrder(o2);

        List<Orders> orderList = dao.getAllOrders();

        for (Orders o : orderList) {
            System.out.println(
                o.getOrderId() + " " +
                o.getProduct() + " " +
                o.getPrice() + " " +
                o.getCustomer().getName()
            );
        }
    }
}
