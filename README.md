# Security Findings and Risk Assessment Report

This project involved reconnaissance, scanning, and enumeration activities conducted on the publicly accessible infrastructure of Kenya Airways. The objective was to gather publicly available information, identify technologies in use, and assess potential security risks without performing any intrusive or unauthorized actions.

## Findings

### 1. Domain and DNS Information

The domain `kenya-airways.com` was successfully resolved to a public IP address using DNS lookup techniques. Additional DNS analysis identified Microsoft 365 Exchange Online as the organization's email service provider through MX record enumeration.

### 2. Subdomain Discovery

Several subdomains associated with the organization were identified through DNS enumeration tools. These subdomains support various organizational services and applications.

### 3. Technology Identification

The following technologies were identified during the assessment:

* Cloudflare
* Nginx 1.24.0 (Ubuntu)
* Amazon Web Services (AWS)
* AWS Elastic Load Balancer (awselb/2.0)
* Amazon CloudFront
* Kubernetes Ingress Controller
* Microsoft 365 Exchange Online

### 4. Service Enumeration

Service detection scans were performed using Nmap. While several services responded to connection attempts, detailed service fingerprinting was limited because many ports returned a `tcpwrapped` status, indicating the presence of security controls.

## Security Risks Identified

### Increased Attack Surface

The presence of multiple publicly accessible subdomains increases the organization's external attack surface. Any unused or poorly maintained subdomain could become a potential security risk.

### Technology Disclosure

Publicly observable technologies may provide attackers with information useful for targeting known vulnerabilities if systems are not regularly updated and patched.

### Cloud Infrastructure Risks

The use of cloud-based services introduces shared responsibility challenges. Misconfigured cloud resources may expose sensitive information or services.

### Email-Based Threats

As the organization relies on Microsoft 365 for email services, phishing, credential theft, and email spoofing remain potential threats that require strong security controls and user awareness.

## Security Controls Observed

The assessment identified several indicators of defensive security measures, including:

* Cloudflare protection services
* Service filtering and restricted fingerprinting
* Load balancing technologies
* Limited service version disclosure

These controls help reduce information exposure and make reconnaissance activities more difficult for potential attackers.

## Conclusion

The findings indicate that Kenya Airways employs modern enterprise technologies and multiple layers of security controls to protect its public-facing infrastructure. While the organization's online presence naturally creates an attack surface through public services and subdomains, the observed security mechanisms demonstrate an effort to minimize information disclosure and enhance overall security posture.

