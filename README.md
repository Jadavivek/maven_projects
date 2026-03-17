package com.seed.dao;
 
import com.seed.entity.Movie;
import com.seed.util.JPAUtil;
import jakarta.persistence.EntityManager;
 
 
public class MovieDAO {
 
    EntityManager em=JPAUtil.getEntityManager();
    
    //insert
    public void saveMovie(Movie movie)
    {
    	em.getTransaction().begin();
    	 em.persist(movie);
    	em.getTransaction().commit();
    	
    	System.out.println("data inserted successfully...");	
    }
   
       
}
 
