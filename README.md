package com.seed.service;

import com.seed.entity.*;
import com.seed.util.JPAUtil;
import jakarta.persistence.EntityManager;

public class InstituteService {

    public void saveInstitute() {

        EntityManager em = JPAUtil.getEntityManager();
        em.getTransaction().begin();

        Address addr = new Address();
        addr.setStreet("MG Road");
        addr.setCity("Hyderabad");
        addr.setCountry("India");
        addr.setPinCode("500001");

        InstituteHistory history = new InstituteHistory();
        history.setFounder("Ramesh Sir");
        history.setHoAddress(addr);

        Institute inst = new Institute();
        inst.setInstituteName("Tech Institute");
        inst.setHistory(history);

        em.persist(inst);

        em.getTransaction().commit();
        em.close();

        System.out.println("Saved Successfully ✅");
    }

    public void getInstitute(int id) {

        EntityManager em = JPAUtil.getEntityManager();

        Institute inst = em.find(Institute.class, id);

        if (inst != null) {
            System.out.println("Institute: " + inst.getInstituteName());
            System.out.println("Founder: " + inst.getHistory().getFounder());
            System.out.println("City: " + inst.getHistory().getHoAddress().getCity());
            System.out.println("Country: " + inst.getHistory().getHoAddress().getCountry());
        } else {
            System.out.println("Not Found ❌");
        }
    }
}
