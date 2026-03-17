package com.seed.entity;

import jakarta.persistence.*;

@Entity
public class Institute {

    @Id
    @GeneratedValue
    private int instituteId;

    private String instituteName;

    @OneToOne(cascade = CascadeType.ALL)
    @PrimaryKeyJoinColumn
    private InstituteHistory history;

    // getters setters
}
