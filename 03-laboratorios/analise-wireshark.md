# 🧪 Laboratório: Análise de Tráfego com Wireshark

## 🎯 Objetivo
Analisar a captura de pacotes de rede para identificar protocolos em tráfego simples e interpretar cabeçalhos.

## 🔍 Filtros Úteis
* `ip.addr == 192.168.1.1` - Filtra tráfego de um IP específico.
* `http` - Exibe apenas requisições e respostas HTTP.
* `dns` - Exibe consultas e respostas de nomes de domínio.
* `tcp.flags.syn == 1` - Identifica tentativas de abertura de conexão TCP.

## 📝 Procedimento
1. Selecionar a interface de rede no Wireshark.
2. Iniciar a captura de pacotes.
3. Aplicar os filtros desejados para isolar a análise.
