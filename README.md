package com.seed.service;
 
import java.util.Map;
import com.seed.model.Device;
 
//service Layer(business logic should go here)
public class AccountService {
	
	private Map<String ,Device> devices;
	
     public AccountService() {
    	 System.out.println("Account service is created");
     }
 
	 public Map<String, Device> getDevices() {
		 return devices;
	 }
 
	 public void setDevices(Map<String, Device> devices) {
		 this.devices = devices;
	 }
     
      //Runtime switching device     
     
	 public void useDevice(String type) {
		
		  Device device=devices.get(type);  //sending request to Map interface
		  
		  if(device!=null) {
			  device.use();
		  }
		  
		  System.out.println("invalid device type....");
		  
	 }
     
}
 
 
 
 
 
 
 
 
 
 
