# Organizational Network Services Infrastructure

## About the Project
This repository contains the practical implementation of a secure enterprise network infrastructure, developed as the final project for the Network Services Administration module in the Cybersecurity program at ISTEC. The solution demonstrates the technical viability of building a highly resilient and secure organizational environment based entirely on Open Source tools.

## Network Architecture & Technologies
The infrastructure was designed on the `10.10.10.0/24` subnet and features the following core components:
* **OPNsense Firewall & Gateway (10.10.10.1):** Centralizes traffic routing, outbound NAT, DNS resolution (Dnsmasq), and dynamic DHCP allocation.
* **Core Web Server (10.10.10.10):** An Ubuntu server running a LAMP stack that hosts a corporate WordPress portal, optimized for high performance using Redis in-memory caching.
* **Nagios Core (10.10.10.30):** Provides active, continuous monitoring of network availability, tracking critical services (HTTP, SSH, PING) and displaying immediate alert states (OK, WARNING, CRITICAL).
* **Wazuh SIEM (10.10.10.40):** A centralized security auditing platform for log collection, anomaly detection, and event management across the infrastructure.

## Security & SOC Integrations
To ensure a strong cybersecurity posture, the following defensive mechanisms were implemented:
* **File Integrity Monitoring (FIM):** The Wazuh agent was explicitly configured to monitor the WordPress public directory (`/var/www/html`) in order to detect unauthorized file modifications in real-time.
* **Real-time Threat Analysis:** Global dashboards visualize security alerts, failed access attempts, and vulnerability statistics.

## Relevance to Offensive Security (Penetration Testing)
While this is fundamentally a defensive and infrastructure project, building it provided deep, practical insights into how enterprise networks are defended. Understanding the intricacies of NAT routing, internal DNS propagation, and SIEM/FIM configurations is essential for an attacker's mindset. It enables the development of more sophisticated penetration testing strategies, focusing on discovering misconfigurations, bypassing firewalls, and evading active monitoring systems like Wazuh.

# Infraestrutura de Serviços de Rede Organizacional

## Sobre o Projeto
Este repositório documenta a implementação prática de uma infraestrutura de rede corporativa segura, desenvolvida como projeto final da unidade curricular de Administração de Serviços de Rede (CTeSP em Cibersegurança - ISTEC). A solução demonstra a viabilidade técnica de criar um ambiente resiliente e seguro baseado integralmente em ferramentas Open Source.

## Arquitetura e Tecnologias
A rede foi estruturada na subnet `10.10.10.0/24` e é composta pelos seguintes servidores centrais:
* **Gateway/Firewall OPNsense (10.10.10.1):** Responsável pelo controlo de tráfego, regras de NAT de saída e serviços de resolução DNS interno e DHCP Dinâmico (via Dnsmasq).
* **Servidor Núcleo Web (10.10.10.10):** Servidor Ubuntu com stack LAMP a alojar um portal WordPress, otimizado com cache em memória via Redis para tempos de resposta superiores.
* **Monitorização Nagios Core (10.10.10.30):** Supervisão contínua e ativa da disponibilidade da rede e serviços críticos (PING, HTTP, SSH), com alertas centralizados.
* **SIEM Wazuh (10.10.10.40):** Central de auditoria de segurança, dedicada à recolha exaustiva de logs, eventos e deteção de anomalias.

## Postura de Segurança e Monitorização (SOC)
O projeto integrou capacidades avançadas de defesa:
* **Monitorização de Integridade de Ficheiros (FIM):** O agente Wazuh foi configurado para monitorizar ativamente a diretoria pública do WordPress (`/var/www/html`), detetando modificações não autorizadas.
* **Análise em Tempo Real:** Criação de dashboards para a visualização intuitiva de alertas de segurança, acessos falhados e estatísticas de vulnerabilidades.

## Relevância para Segurança Ofensiva (Pentesting)
Embora se trate de um projeto de implementação de infraestruturas, desenhar e configurar esta rede permitiu compreender a fundo como os ambientes corporativos operam e se defendem. Conhecer a arquitetura de firewalls (OPNsense), sistemas de resolução de nomes e, sobretudo, os mecanismos de deteção de um SIEM e FIM, é um conhecimento vital para a Segurança Ofensiva. Esta base teórica e prática permite simular ataques mais realistas, identificar falhas de arquitetura e testar técnicas avançadas de evasão contra sistemas de monitorização de segurança.
