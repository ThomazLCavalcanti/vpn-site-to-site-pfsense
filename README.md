
# VPN Site-to-Site com pfSense

## 📌 Descrição

Este projeto demonstra a implementação de uma VPN Site-to-Site utilizando dois firewalls pfSense em ambientes virtualizados. A conexão VPN permite comunicação segura entre duas redes distintas, como se estivessem na mesma LAN, simulando dois escritórios remotos interligados. O foco do projeto é aplicar conceitos de segurança de redes, roteamento e conectividade entre sites diferentes.

## 🎯 Objetivos

- Demonstrar domínio prático em configuração de VPN (IPsec ou OpenVPN)
- Aplicar regras de firewall para controle de tráfego
- Testar a conectividade entre as redes após o estabelecimento do túnel
- Criar documentação clara, com topologia e evidências funcionais

## 🧰 Tecnologias e Ferramentas

- pfSense (última versão estável)
- VirtualBox ou Proxmox (para virtualização)
- Cliente Linux (para testes de conectividade)
- Editor de texto (para edição de regras e scripts)

## 🌐 Topologia

A topologia é composta por dois sites simulando escritórios distintos:

- **Site 1:** pfSense com LAN 192.168.10.0/24
- **Site 2:** pfSense com LAN 192.168.20.0/24
- Ambos conectados via IP público simulado no ambiente virtual

A imagem `docs/diagrama_topologia.png` ilustra a arquitetura da rede.

## 🔐 VPN

A VPN foi implementada utilizando **IPsec Tunnel Mode**, com autenticação mútua por PSK (pre-shared key) e políticas de criptografia seguras (AES-256, SHA256, DH Group 14).

## 🔎 Testes Realizados

- Ping entre hosts dos dois sites
- Testes de perda de pacotes e latência
- Acesso remoto via IP entre as redes
- Testes de fallback da VPN (simulação de queda)

As evidências estão documentadas na pasta `/docs/` e os comandos utilizados nos testes em `/testes/`.

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
