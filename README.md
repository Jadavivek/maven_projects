package com.seed.config;
 
import java.util.HashMap;
import java.util.Map;
 
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
 
import com.seed.model.Computer;
import com.seed.model.Device;
import com.seed.model.Laptop;
import com.seed.service.AccountService;
 
//Centerlized bean creation(Config Layer)
 
@Configuration
public class AppConfig {
  
	@Bean
     public Device computer() {
		return new Computer();
	}
	
	@Bean
    public Device laptop() {
		return new Laptop();
	}
	
	@Bean
	public AccountService accountService() {
		
		AccountService service=new AccountService();
		
		Map<String,Device> map=new HashMap<>();
		
		
		map.put("computer", computer());
		map.put("laptop", laptop());
		
		service.setDevices(map);
		
		return service;
		
	}
	
	
	
}
 
 
 
 
 
 
 
 
 
 
 
