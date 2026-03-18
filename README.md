package com.seed;
 
import org.springframework.boot.SpringApplication;

import org.springframework.boot.autoconfigure.SpringBootApplication;

import org.springframework.context.ConfigurableApplicationContext;
 
@SpringBootApplication

public class Demo3WithQualifierApplication {
 
	public static void main(String[] args) 

	{

		ConfigurableApplicationContext context= SpringApplication.run(Demo3WithQualifierApplication.class, args);

		Bank b1=context.getBean(Bank.class);

		   b1.show();

		Bank b2=context.getBean(Bank.class);

			   b2.show();   

	}
 
}

 
