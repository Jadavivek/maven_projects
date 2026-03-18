package com.seed;
 
import org.springframework.stereotype.Component;
 
@Component("comp1")
public class Computer {
   
	private int id;
	private String brand;
	
	public void display() {
		System.out.println("Computer Started...");
	}
	
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public String getBrand() {
		return brand;
	}
	public void setBrand(String brand) {
		this.brand = brand;
	}
	@Override
	public String toString() {
		return "Computer [id=" + id + ", brand=" + brand + "]";
	}
	
	
	
}
 
 
