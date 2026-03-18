package com.seed;
 
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Component;
 
@Component
@Scope(value="prototype")
public class Bank {
   
	private int bid;
	private String name;
	private double balance;
	
	@Autowired   //search bean by type
	@Qualifier("comp1")    //search bean by name
	private Computer comp;
	
	public Bank() {
		System.out.println("object created");
	}
 
	public void show() {
		System.out.println("Bank Opened...");
		comp.display();
	}
	
	public int getBid() {
		return bid;
	}
 
	public void setBid(int bid) {
		this.bid = bid;
	}
 
	public String getName() {
		return name;
	}
 
	public void setName(String name) {
		this.name = name;
	}
 
	public double getBalance() {
		return balance;
	}
 
	public void setBalance(double balance) {
		this.balance = balance;
	}
 
	public Computer getComp() {
		return comp;
	}
 
	public void setComp(Computer comp) {
		this.comp = comp;
	}
 
	@Override
	public String toString() {
		return "Bank [bid=" + bid + ", name=" + name + ", balance=" + balance + ", comp=" + comp + "]";
	}
	
	
}
 
 
