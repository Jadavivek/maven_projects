package com.seed.client;

import com.seed.entity.*;
import com.seed.util.JPAUtil;
import jakarta.persistence.EntityManager;

public class Client1 {

    public static void main(String[] args) {

        EntityManager em = JPAUtil.getEntityManager();
        em.getTransaction().begin();

        Address addr = new Address();
        addr.setCity("Mumbai");
        addr.setCountry("India");

        InstituteHistory history = new InstituteHistory();
        history.setFounder("ABC Sir");
        history.setHoAddress(addr);

        Institute inst = new Institute();
        inst.setInstituteName("Seed Institute");
        inst.setHistory(history);

        em.persist(inst);

        em.getTransaction().commit();
        em.close();

        System.out.println("Saved Successfully!");
    }
}
