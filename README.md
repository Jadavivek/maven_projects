package com.seed.entity;
 
import java.util.HashSet;
import java.util.Set;
 
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.Id;
import jakarta.persistence.ManyToMany;
 
@Entity
public class Actor {
   
	@Id
	@GeneratedValue
	private int actorId;
	
	private String name;
 
	@ManyToMany(mappedBy = "actors")
	private Set<Movie> movies=new HashSet<>();
 
	
	public Set<Movie> getMovies() {
		return movies;
	}
 
	public void setMovies(Set<Movie> movies) {
		this.movies = movies;
	}
 
	public int getActorId() {
		return actorId;
	}
 
	public String getName() {
		return name;
	}
 
	public void setActorId(int actorId) {
		this.actorId = actorId;
	}
 
	public void setName(String name) {
		this.name = name;
	}
	
	
}
 
 
