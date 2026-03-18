package com.seed;
 
import java.util.Scanner;
 
import org.springframework.boot.SpringApplication;

import org.springframework.boot.autoconfigure.SpringBootApplication;

import org.springframework.context.ConfigurableApplicationContext;
 
import com.seed.service.AccountService;
 
@SpringBootApplication

public class Demo3WithOutQualifier1Application {
 
	public static void main(String[] args) {

	  ConfigurableApplicationContext context=	SpringApplication.run(Demo3WithOutQualifier1Application.class, args);

	  AccountService service=context.getBean(AccountService.class);

	  Scanner sc=new Scanner(System.in);

	  System.out.println("enter device (computer/laptop)");

	  String input=sc.nextLine();

	  service.useDevice(input.toLowerCase());

	  sc.close();

	}
 
}

 
