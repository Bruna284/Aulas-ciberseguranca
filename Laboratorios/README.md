<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1D3A,50:1A365D,100:2A4365&height=220&section=header&text=Laborat%C3%B3rios%20Pr%C3%A1ticos&fontSize=42&fontColor=FFFFFF&fontAlignY=35&desc=M%C3%B3dulo%2005%20%7C%20Simula%C3%A7%C3%B5es,%20Capturas%20e%20Configura%C3%A7%C3%B5es&descAlignY=55&descSize=18&descColor=58A6FF&animation=fadeIn" width="100%" />

<img src="https://img.shields.io/badge/Packet_Tracer-161B22?style=for-the-badge&logo=cisco&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/Wireshark-161B22?style=for-the-badge&logo=wireshark&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/Hands_On-161B22?style=for-the-badge&logo=linux&logoColor=58A6FF" />

</div>

<br>

## 📌 Visão Geral
Esta pasta é dedicada ao registro de atividades práticas, topologias de rede desenvolvidas e testes de análise de tráfego. O objetivo é documentar o aprendizado executado em ambientes simulados (**Cisco Packet Tracer**) e em ferramentas de inspeção de pacotes (**Wireshark**).

---

## 🧪 Atividades & Laboratórios Executados

| ID | Nome do Laboratório | Ferramenta | Foco de Estudo | Status |
| :--- | :--- | :--- | :--- | :--- |
| **LAB-01** | Configuração Inicial de Switch e Roteador | Packet Tracer | Hostname, Senhas, Banner e SSH v2 | 🟢 Concluído |
| **LAB-02** | Análise de Tráfego HTTP e DNS | Wireshark | Inspeção de cabeçalhos e consultas DNS | 🟢 Concluído |
| **LAB-03** | Endereçamento e Sub-redes IPv4 | Packet Tracer | Atribuição estática e servidor DHCP | 🟢 Concluído |
| **LAB-04** | Captura do Handshake 3-Way do TCP | Wireshark | Sinalização SYN, SYN-ACK e ACK | 🟢 Concluído |

---

## 🔬 Destaque de Laboratório: Análise de Tráfego com Wireshark

### 🎯 Objetivo
Capturar e analisar o fluxo de comunicação de um cliente buscando resolução de nome via **DNS** e acesso a uma página **HTTP/HTTPS**.

```text
  [ Cliente ] ──── (1) DNS Query (UDP 53) ────> [ Servidor DNS ]
  [ Cliente ] <─── (2) DNS Response ─────────── [ Servidor DNS ]
  
  [ Cliente ] ──── (3) TCP SYN ────────────────> [ Servidor Web ]
  [ Cliente ] <─── (4) TCP SYN-ACK ──────────── [ Servidor Web ]
  [ Cliente ] ──── (5) TCP ACK ────────────────> [ Servidor Web ]
