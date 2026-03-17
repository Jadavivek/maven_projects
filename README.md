package com.seed;
 
import com.seed.dao.MovieDAO;
import com.seed.entity.Actor;
import com.seed.entity.Movie;
 
public class App
{
    public static void main( String[] args )
    {
         //Actors
    	
    	Actor a1=new Actor();
    	   a1.setName("Shah Rukh Khan");
     	
    	Actor a2=new Actor();
    	   a2.setName("Kajol");
    	
        Actor a3=new Actor();
    	   a3.setName("Ranbir Kapoor");
    	   
    	Actor a4=new Actor();
    	   a4.setName("Alia bhat");  
    	   
    	Actor a5=new Actor();
    	   a5.setName("Amir Khan");
    	   
    	//Movie
    	   
    	 Movie m1=new Movie();
    	     m1.setMovieName("DDLJ");
    	
    	 Movie m2=new Movie();
    	 	m2.setMovieName("Brmhastra");
    	     
    	 Movie m3=new Movie();
    	     m3.setMovieName("Dangal");
    	     
    	 Movie m4=new Movie();
    	     m4.setMovieName("My name is khan");
    	     
    	//Relationship//
    	     
    	 //DDLJ -Shah Rukh Khan,Kajol
    	     
    	 m1.getActors().add(a1);
    	 m1.getActors().add(a2);
    	 a1.getMovies().add(m1);
    	 a2.getMovies().add(m1);
    	
    	
     	 //Brmhastra -Ranbir Kapoor,Alia bhat
	     
    	 m2.getActors().add(a3);
    	 m2.getActors().add(a4);
    	 a3.getMovies().add(m2);
    	 a4.getMovies().add(m2);
    	
    	 //Dangal -amir Khan
    	 m3.getActors().add(a5);
    	 a5.getMovies().add(m3);
    	
    	 //My name is khan
    	 m4.getActors().add(a1);
    	 a1.getMovies().add(m4);  
    	
    	
    	 //save data
    	
    	 MovieDAO dao=new MovieDAO();
    	
    	 dao.saveMovie(m1);
    	 dao.saveMovie(m2);
    	 dao.saveMovie(m3);
    	 dao.saveMovie(m4);
    	
    }
}
 
 
 
 
 
 
 
 
