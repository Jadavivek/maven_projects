package com.seed.client;

import com.seed.entity.*;
import com.seed.util.JPAUtil;
import jakarta.persistence.EntityManager;
import java.util.Scanner;

public class Client2 {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter instituteId:");
        int id = sc.nextInt();

        EntityManager em = JPAUtil.getEntityManager();

        Institute inst = em.find(Institute.class, id);

        System.out.println("Institute: " + inst.getInstituteName());
        System.out.println("Founder: " + inst.getHistory().getFounder());
        System.out.println("City: " + inst.getHistory().getHoAddress().getCity());
        System.out.println("Country: " + inst.getHistory().getHoAddress().getCountry());
    }
}
