---
title: Preventive Security Controls
date: 2024-11-23 10H:21:00 -0300
categories: [Cybersecurity, Preventive Controls]
tags: [cybersecurity, preventive-controls, devsecops, devsecops-tools]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Airports_Network_Map.png/640px-Airports_Network_Map.png
  alt: Picture
---

# Some preventive controls for the security of the organization

To mitigate security flaws before they reach production, it is crucial to integrate security controls into the DevOps.

1. **Static Application Security Testing (SAST)**:
  - Integrate SAST tools to analyze source code for known vulnerabilities without executing the code. These tools can detect issues like buffer overflows, SQL injection, and cross-site scripting (XSS).
    1. Example of Useful Tools:
      - [SonarQube](https://www.sonarqube.org/)
      - [Checkmarx](https://www.checkmarx.com/)
      - [AWS CodeGuru Reviewer](https://aws.amazon.com/codeguru/)
    2. Learning resources:
      - [SonarQube Documentation](https://docs.sonarqube.org/latest/)
      - [Checkmarx Learning Center](https://checkmarx.com/resources/)
      - [AWS CodeGuru Documentation](https://docs.aws.amazon.com/codeguru/latest/reviewer-ug/what-is-codeguru-reviewer.html)

2. **Dynamic Application Security Testing (DAST)**:
  - Use DAST tools to test running applications for vulnerabilities by simulating external attacks. This helps identify issues that may not be visible in the source code alone.
  2.1. Example of Useful Tools:
    - [OWASP ZAP](https://www.zaproxy.org/)
    - [Burp Suite](https://portswigger.net/burp)
  2.2. Learning resources:
    - [RedHat - Application Analysis](https://www.redhat.com/en/blog/application-analysis-devsecops-life-cycle)

3. **Software Composition Analysis (SCA)**:
  - Implement SCA tools to scan for vulnerabilities in third-party libraries and dependencies. This ensures that all components used in the application are secure and up-to-date.
  3.1. Example of Useful Tools:
    - [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)
    - [AWS CodeArtifact](https://aws.amazon.com/codeartifact/)
  3.2. Learning resources:
    - [OWASP Dependency-Check Documentation](https://jeremylong.github.io/DependencyCheck/)
    - [AWS CodeArtifact Documentation](https://docs.aws.amazon.com/codeartifact/)

4. **Continuous Integration/Continuous Deployment (CI/CD) Security**:
  - Integrate security checks into the CI/CD pipeline to automatically scan for vulnerabilities during the build and deployment processes. This includes running SAST, DAST, and SCA tools as part of the pipeline.
  4.1. Example of Useful Tools:
    - [Jenkins](https://www.jenkins.io/)
    - [GitLab CI/CD](https://docs.gitlab.com/ee/ci/)
    - [AWS CodePipeline](https://aws.amazon.com/codepipeline/)
  4.2. Learning resources:
    - [Jenkins Security](https://www.jenkins.io/doc/book/security/)
    - [GitLab CI/CD Documentation](https://docs.gitlab.com/ee/ci/)
    - [AWS CodePipeline Documentation](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html)

5. **Container Security**:
  - If using containerization, employ container security tools to scan container images for vulnerabilities and ensure they adhere to security best practices.
  5.1. Example of Useful Tools:
    - [Docker Bench for Security](https://github.com/docker/docker-bench-security)
    - [Clair](https://github.com/quay/clair)
    - [Amazon Inspector](https://aws.amazon.com/inspector/)
  5.2. Learning resources:
    - [Docker Security](https://docs.docker.com/engine/security/security/)
    - [Clair Documentation](https://quay.github.io/clair/)
    - [Amazon Inspector Documentation](https://docs.aws.amazon.com/inspector/latest/userguide/inspector_introduction.html)

6. **Infrastructure as Code (IaC) Security**:
  - Use IaC security tools to scan configuration files (e.g., Terraform, Ansible) for misconfigurations that could lead to security vulnerabilities.
  6.1. Example of Useful Tools:
    - [Terraform Sentinel](https://www.terraform.io/docs/cloud/sentinel/index.html)
    - [Ansible-Lint](https://github.com/ansible/ansible-lint)
    - [AWS Config](https://aws.amazon.com/config/)
  6.2. Learning resources:
    - [Terraform Security Best Practices](https://learn.hashicorp.com/collections/terraform/security)
    - [Ansible-Lint Documentation](https://ansible-lint.readthedocs.io/)
    - [AWS Config Documentation](https://docs.aws.amazon.com/config/latest/developerguide/WhatIsConfig.html)

7. **Regular Security Audits and Penetration Testing**:
  - Conduct regular security audits and penetration testing to identify and remediate vulnerabilities that automated tools might miss.
  7.1. Example of Useful Tools:
    - [Metasploit](https://www.metasploit.com/)
    - [Nessus](https://www.tenable.com/products/nessus)
  7.2. Learning resources:
    - [Metasploit Documentation](https://docs.rapid7.com/metasploit/)
    - [Nessus Documentation](https://docs.tenable.com/nessus/)

By incorporating these security controls into the DevOps lifecycle, organizations can significantly reduce the risk of security flaws reaching production, thereby improving the overall security posture of their applications and, consequently, the organization.