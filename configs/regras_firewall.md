# Regras de Firewall – VPN Site-to-Site com pfSense

Este documento descreve as regras de firewall configuradas em cada lado da VPN para garantir a conectividade e a segurança entre os dois sites (Site 1 e Site 2).

---

## 🔐 Site 1 – pfSense

### 🧩 Interface LAN
Permitir tráfego interno:

- **Action:** Pass  
- **Interface:** LAN  
- **Source:** LAN net  
- **Destination:** any  
- **Protocol:** any  
- **Description:** Permitir acesso da LAN para qualquer destino  

### 🔄 Interface OpenVPN ou IPsec
Permitir tráfego da VPN:

- **Action:** Pass  
- **Interface:** OpenVPN (ou IPsec, dependendo da escolha)  
- **Source:** Sub-rede remota (ex: 192.168.20.0/24)  
- **Destination:** LAN net (ex: 192.168.10.0/24)  
- **Protocol:** any  
- **Description:** Permitir tráfego da VPN para a LAN  

---

## 🔐 Site 2 – pfSense

### 🧩 Interface LAN
Permitir tráfego interno:

- **Action:** Pass  
- **Interface:** LAN  
- **Source:** LAN net  
- **Destination:** any  
- **Protocol:** any  
- **Description:** Permitir acesso da LAN para qualquer destino  

### 🔄 Interface OpenVPN ou IPsec
Permitir tráfego da VPN:

- **Action:** Pass  
- **Interface:** OpenVPN (ou IPsec)  
- **Source:** Sub-rede remota (ex: 192.168.10.0/24)  
- **Destination:** LAN net (ex: 192.168.20.0/24)  
- **Protocol:** any  
- **Description:** Permitir tráfego da VPN para a LAN  

---

## ✅ Observações

- As interfaces de VPN variam conforme a tecnologia usada: OpenVPN ou IPsec.
- Certifique-se de aplicar e salvar as regras após adicioná-las.
- Para aumentar a segurança, é possível restringir protocolos ou portas específicas conforme o cenário.

---