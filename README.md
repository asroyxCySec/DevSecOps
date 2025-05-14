# DevSecOps
# Disclaimer: Tools di buat oleh saya sendiri dengan tujuan challenge diri sendiri menjadi lebih baik😊🙏

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
  ┌─────▼─────┐      ┌─────▼─────┐      ┌─────▼─────┐
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

