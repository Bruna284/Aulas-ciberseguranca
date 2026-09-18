<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1D3A,50:1A365D,100:2A4365&height=220&section=header&text=Dispositivos%20%26%20Configura%C3%A7%C3%A3o%20Inicial&fontSize=38&fontColor=FFFFFF&fontAlignY=35&desc=M%C3%B3dulo%2003%20%7C%20Equipamentos%20de%20Infraestrutura%20e%20Sistemas%20Operacionais&descAlignY=55&descSize=18&descColor=58A6FF&animation=fadeIn" width="100%" />

<img src="https://img.shields.io/badge/Cisco_IOS-161B22?style=for-the-badge&logo=cisco&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/Switches_&_Routers-161B22?style=for-the-badge&logo=hardware&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/CLI_Config-161B22?style=for-the-badge&logo=gnu-bash&logoColor=58A6FF" />

</div>

<br>

## 📌 Visão Geral
Neste módulo, estudamos a arquitetura física e lógica dos principais dispositivos que compõem uma infraestrutura de rede corporativa (Switches, Roteadores, Firewalls e Access Points). Também abordamos o sistema operacional **Cisco IOS**, seus modos de execução e a sequência de comandos essenciais para realizar a **configuração inicial e o endurecimento (*hardening*) de segurança** nos equipamentos.

---

## 🧱 Dispositivos de Infraestrutura de Rede

Cada dispositivo atua em uma camada específica do Modelo OSI e desempenha um papel fundamental no encaminhamento de tráfego:

| Dispositivo | Camada OSI | Função Principal | Tabela Utilizada |
| :--- | :--- | :--- | :--- |
| **Hub** | Camada 1 (Física) | Repetidor de sinal (Obsoleto). Envia dados por *flooding* para todas as portas. | Nenhuma |
| **Switch (L2)** | Camada 2 (Enlace) | Interconecta dispositivos na mesma rede local (LAN) usando endereços MAC. | **Tabela MAC / CAM** |
| **Switch Layer 3** | Camadas 2 e 3 | Executa comutação rápida em L2 e roteamento inter-VLANs em L3. | **Tabela MAC / Tabela FIB** |
| **Roteador** | Camada 3 (Rede) | Interconecta redes distintas e determina a melhor rota para pacotes IP. | **Tabela de Roteamento** |
| **Firewall** | Camadas 3 a 7 | Inspeciona o tráfego e aplica políticas de acesso (Ação: Permite/Bloqueia). | **Tabela de Estados (Stateful)** |
| **Access Point (AP)** | Camada 2 (Enlace) | Converte sinal de rádio Wi-Fi (802.11) em quadros Ethernet (802.3). | Tabela de Associação de Clientes |

---

## 🧠 Arquitetura de Memória e Processo de Boot (Cisco IOS)

Entender as memórias de um dispositivo Cisco é indispensável para evitar perda de configurações durante quedas de energia ou reinicializações:

- **RAM (Random Access Memory):** Armazena a configuração em execução (`running-config`), tabelas de roteamento e ARP. O conteúdo é perdido ao desligar.
- **NVRAM (Non-Volatile RAM):** Armazena a configuração de inicialização (`startup-config`) mantida permanentemente.
- **Flash:** Memória EEPROM contendo a imagem do sistema operacional Cisco IOS e arquivos do sistema.
- **ROM (Read-Only Memory):** Armazena o código de diagnóstico **POST** (*Power-On Self-Test*) e o **ROMMON** (modo de recuperação do sistema).

```text
 ┌────────────────────────────────────────────────────────────────────────┐
 │                      FLUXO DE BOOT DO CISCO IOS                        │
 └────────────────────────────────────────────────────────────────────────┘
                                     │
 1. Execução do POST (Hardware Check na ROM)
                                     │
 2. Localização e carregamento do Bootstrap (ROM)
                                     │
 3. Localização da imagem do Cisco IOS (Memória Flash) ──> Carregamento na RAM
                                     │
 4. Busca pelo arquivo 'startup-config' na NVRAM ───────> Copia para 'running-config'
