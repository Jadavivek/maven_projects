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

    // ✅ getters & setters
    public int getInstituteId() { return instituteId; }
    public void setInstituteId(int instituteId) { this.instituteId = instituteId; }

    public String getInstituteName() { return instituteName; }
    public void setInstituteName(String instituteName) { this.instituteName = instituteName; }

    public InstituteHistory getHistory() { return history; }
    public void setHistory(InstituteHistory history) { this.history = history; }
}
