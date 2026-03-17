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

    // ✅ getters & setters
    public int getInstituteId() { return instituteId; }
    public void setInstituteId(int instituteId) { this.instituteId = instituteId; }

    public String getFounder() { return founder; }
    public void setFounder(String founder) { this.founder = founder; }

    public Date getFoundationDate() { return foundationDate; }
    public void setFoundationDate(Date foundationDate) { this.foundationDate = foundationDate; }

    public Address getHoAddress() { return hoAddress; }
    public void setHoAddress(Address hoAddress) { this.hoAddress = hoAddress; }

    public Institute getInstitute() { return institute; }
    public void setInstitute(Institute institute) { this.institute = institute; }
}
