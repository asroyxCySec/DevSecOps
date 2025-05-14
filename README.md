# DevSecOps

> Disclaimer: Tools dibuat oleh saya sendiri dengan tujuan challenge diri sendiri menjadi lebih baik 😊 🙏

## 1. Arsitektur DevSecOps Overview

                                               ┌──────────────────────────────┐
                                               │         Developers           │
                                               └─────────────┬────────────────┘
                                                             │
                                          ┌──────────────────┴──────────────────┐
                                          │            Source Code Repo         │ (GitHub / GitLab)
                                          └──────────────────┬──────────────────┘
                                                             │
                                              ┌──────────────┴──────────────┐
                                              │         CI/CD Pipeline      │ (Jenkins / GitLab CI / GitHub Actions)
                                              └──────────────┬──────────────┘
                                                             │
                                          ┌──────────────────┼──────────────────┐
                                          │                  │                  │
                                          │                  │                  │
                                    ┌─────▼─────┐      ┌─────▼──────┐     ┌─────▼─────┐
                                    │    SAST   │      │    SCA     │     │    DAST   │
                                    │ (Semgrep) │      │(Syft/Grype)│     │(OWASP ZAP │
                                    └───────────┘      └────────────┘     └───────────┘
                                                             │
                                                      ┌──────▼──────┐
                                                      │Vulnerability│
                                                      │   Scanning  │ (OpenVAS/Wazuh)
                                                      └──────┬──────┘
                                                             │
                                                      ┌──────▼──────┐
                                                      │Monitoring & │
                                                      │   Logging   │ (ELK Stack/Wazuh)
                                                      └──────┬──────┘
                                                             │
                                                      ┌──────▼──────┐
                                                      │ SOAR & IR   │ (TheHive + Cortex) 
                                                      └─────────────┘ 



## 2. Komponen & Tools
> ![image](https://github.com/user-attachments/assets/78dcef24-b1c7-4dae-8ee0-293a040f727c)


## 3. Workflow DevSecOps (End-to-End)
> ✅ Kode Commit → Build → Security Check → Deploy → Monitor
> 1. Kode di-push ke repository (GitLab/GitHub).
> 2. CI/CD Pipeline berjalan otomatis: (Jalankan SAST scan pakai Semgrep. Jalankan SCA scan pakai Syft & Grype).
> 3. Build container image → scan dengan Trivy.
> 4. Deploy ke staging → lakukan DAST otomatis pakai OWASP ZAP.
> 5. Jalankan vulnerability scan infrastruktur pakai OpenVAS.
> 6. Monitoring log aplikasi & sistem via ELK + Wazuh.
> 7. SOAR automation untuk alert & response via TheHive + Cortex.
> 8. Continuous Risk Assessment → Threat modeling dengan OWASP Threat Dragon.


## 4. Dashboard & Reporting
> Kibana → Visualisasi log, security events, SIEM alerts.
> Grafana → Custom monitoring dashboards (CI/CD pipeline status, vulnerabilities metrics).
> TheHive UI → Incident management & case tracking.


## 5. Best Practices Tambahan
> ![image](https://github.com/user-attachments/assets/a3ba7288-a717-4ed3-a13b-b9741bb01c0c)


## 6. Estimated Deployment (DevSecOps Open-Source Stack)
> ![image](https://github.com/user-attachments/assets/d4f84b51-0469-4eb4-98ca-8a049148c7b8)
