package com.seed.entity;

import jakarta.persistence.*;
import java.util.Date;

@Entity
public class InstituteHistory {

    @Id
    private int instituteId;

    private String founder;

    @Temporal(TemporalType.DATE)
    private Date foundationDate;

    @Embedded
    private Address hoAddress;

    @OneToOne(mappedBy = "history")
    private Institute institute;

    // getters & setters
}
