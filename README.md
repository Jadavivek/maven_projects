package com.seed.dao;

import java.util.List;

import com.seed.entity.Orders;
import com.seed.util.JPAUtil;

import jakarta.persistence.*;

public class OrderDAO {

    // SAVE
    public void saveOrder(Orders order) {
        EntityManager em = JPAUtil.getEntityManager();
        EntityTransaction tx = em.getTransaction();

        tx.begin();
        em.persist(order);
        tx.commit();

        em.close();
    }

    // FETCH ALL
    public List<Orders> getAllOrders() {
        EntityManager em = JPAUtil.getEntityManager();

        List<Orders> list =
                em.createQuery("from Orders", Orders.class).getResultList();

        em.close();
        return list;
    }
}

