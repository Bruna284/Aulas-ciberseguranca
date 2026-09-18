<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1D3A,50:1A365D,100:2A4365&height=220&section=header&text=Redes%20%26%20Protocolos&fontSize=46&fontColor=FFFFFF&fontAlignY=35&desc=Fundamentos%20de%20Comunica%C3%A7%C3%A3o,%20Arquitetura%20e%20Troubleshooting&descAlignY=55&descSize=18&descColor=58A6FF&animation=fadeIn" width="100%" />

<img src="https://img.shields.io/badge/Cisco_NetAcad-161B22?style=for-the-badge&logo=cisco&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/TCP/IP_Stack-161B22?style=for-the-badge&logo=sitemap&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/Wireshark_Ready-161B22?style=for-the-badge&logo=wireshark&logoColor=58A6FF" />

</div>

<br>

## 📌 Visão Geral
Este módulo reúne o estudo aprofundado sobre como os computadores se comunicam em rede. O foco principal é entender a estrutura dos modelos **OSI** e **TCP/IP**, os serviços essenciais de infraestrutura (**DHCP**, **DNS**, **ARP**) e a diferença prática entre os protocolos da camada de transporte (**TCP** e **UDP**).

---

## 🏗️ Modelos de Referência: OSI vs TCP/IP

A comunicação em rede acontece por meio do processo de **Encapsulamento** (onde cada camada adiciona seu próprio cabeçalho aos dados) e **Desencapsulamento** (na recepção).

| Camada OSI | PDU (Unidade de Dados) | Protocolos / Tecnologias | Função Principal |
| :--- | :--- | :--- | :--- |
| **7. Aplicação** | Dados | HTTP, HTTPS, DNS, DHCP, SSH, FTP | Interface direta com a aplicação final. |
| **6. Apresentação** | Dados | SSL/TLS, ASCII, JPEG | Formatação, compressão e criptografia de dados. |
| **5. Sessão** | Dados | NetBIOS, RPC | Abertura, manutenção e encerramento de conexões. |
| **4. Transporte** | Segmento (TCP) / Datagrama (UDP) | TCP, UDP | Controle de fluxo, ordenação e portas lógicas. |
| **3. Rede** | Pacote | IP (IPv4/IPv6), ICMP, ARP, IPsec | Endereçamento lógico e roteamento entre redes. |
| **2. Enlace** | Quadro (Frame) | Ethernet, Wi-Fi (802.11), VLANs | Endereçamento físico (MAC) e controle de acesso ao meio. |
| **1. Física** | Bits | Cabos UTP, Fibra Óptica, Sinal de Rádio | Transmissão de sinais elétricos, ópticos ou eletromagnéticos. |

---

## ⚡ Camada de Transporte: TCP vs UDP

A camada de transporte utiliza o conceito de **Portas Lógicas** (de `0` a `65535`) para direcionar o tráfego para a aplicação correta.

```text
 ┌────────────────────────────────────────────────────────────────────────┐
 │                              MENSAGEM                                 │
 └────────────────────────────────────────────────────────────────────────┘
                                     │
            ┌────────────────────────┴────────────────────────┐
            ▼                                                 ▼
   [ TCP - Orientado à Conexão ]                    [ UDP - Sem Conexão ]
   - Confiável (Garante entrega)                    - Não confiável (Best effort)
   - Controle de fluxo e erros                      - Sem controle de ordenação
   - Overhead maior (Cabeçalho de 20B)              - Overhead mínimo (Cabeçalho de 8B)
   - Ex: Web (HTTPS), E-mail, SSH                   - Ex: Streaming, DNS, VoIP
