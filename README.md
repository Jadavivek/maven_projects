package com.seed.entity;
 
import java.util.HashSet;
import java.util.Set;
 
import jakarta.persistence.CascadeType;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.Id;
import jakarta.persistence.JoinColumn;
import jakarta.persistence.JoinTable;
import jakarta.persistence.ManyToMany;
 
@Entity
public class Movie {
   
	@Id
	@GeneratedValue
	private int movieId;
	
	private String movieName;
	
	@ManyToMany(cascade = CascadeType.ALL)
	@JoinTable(name="movie_actor",
	            joinColumns = @JoinColumn(name="movie_id"),
	            inverseJoinColumns = @JoinColumn(name="actor_id") )
	private Set<Actor> actors=new HashSet<>();
 
	
	public Set<Actor> getActors() {
		return actors;
	}
 
	public void setActors(Set<Actor> actors) {
		this.actors = actors;
	}
 
	public int getMovieId() {
		return movieId;
	}
 
	public String getMovieName() {
		return movieName;
	}
 
	public void setMovieId(int movieId) {
		this.movieId = movieId;
	}
 
	public void setMovieName(String movieName) {
		this.movieName = movieName;
	}
	
	
	
	
}
 
 
