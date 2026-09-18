<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1D3A,50:1A365D,100:2A4365&height=220&section=header&text=Seguran%C3%A7a%20de%20Endpoint&fontSize=40&fontColor=FFFFFF&fontAlignY=35&desc=M%C3%B3dulo%2004%20%7C%20Prote%C3%A7%C3%A3o%20de%20Dispositivos,%20EDR,%20XDR%20e%20Hardening&descAlignY=55&descSize=18&descColor=58A6FF&animation=fadeIn" width="100%" />

<img src="https://img.shields.io/badge/Endpoint_Security-161B22?style=for-the-badge&logo=shield&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/EDR_&_XDR-161B22?style=for-the-badge&logo=target&logoColor=58A6FF" />
<img src="https://img.shields.io/badge/System_Hardening-161B22?style=for-the-badge&logo=linux&logoColor=58A6FF" />

</div>

<br>

## 📌 Visão Geral
Endpoints (estações de trabalho, servidores, laptops e dispositivos móveis) são a porta de entrada primária para a grande maioria das invasões corporativas. Este módulo abrange desde a evolução da proteção de ativos finais até o uso de ferramentas avançadas de **Detecção e Resposta (EDR/XDR)**, políticas de **Hardening** de Sistemas Operacionais e mitigação de exploração de vulnerabilidades.

---

## 🛡️ Evolução da Proteção: Antivírus vs EDR vs XDR

A proteção de dispositivos finais evoluiu de abordagens reativas baseadas em assinaturas para sistemas baseados em inteligência artificial e análise comportamental:

| Tecnologia | Abordagem Principal | Mecanismo de Detecção | Capacidade de Resposta |
| :--- | :--- | :--- | :--- |
| **Antivírus Tradicional (EPP)** | Reativa / Conhecida | Assinaturas de arquivos e hashes estáticos. | Quarentena ou exclusão do arquivo malicioso. |
| **EDR (Endpoint Detection & Response)** | Proativa / Comportamental | Análise de comportamento no host, heurística e IA. | Isolamento de rede, término de processos e investigação forense. |
| **XDR (Extended Detection & Response)** | Holística / Correlacionada | Integra dados de Endpoints, Redes, Nuvem e E-mails. | Resposta automatizada orquestrada em toda a infraestrutura. |

---

## 🔧 Pilares do System Hardening (Endurecimento de Sistemas)

*Hardening* é o processo de mapear e reduzir a superfície de ataque de um sistema operacional, desativando recursos desnecessários e aplicando restrições de acesso.

```text
  [ Sistema Padrão / Vulnerável ] 
                 │
                 ├──> Desativação de Serviços Desnecessários (Ex: Telnet, SMBv1)
                 ├──> Configuração de Firewall Host-Based (Windows Firewall / UFW)
                 ├──> Gestão Rigorosa de Patches e Atualizações
                 ├──> Aplicação do Princípio do Menor Privilégio (LUA/Sudo)
                 │
                 ▼
  [ Sistema Endurecido / Hardened ]
