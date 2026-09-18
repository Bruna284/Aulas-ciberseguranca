! --- 1. Definição do Nome do Dispositivo e Domínio ---
Switch> enable
Switch# configure terminal
Switch(config)# hostname SW-CORE-01
SW-CORE-01(config)# ip domain-name empresa.local

! --- 2. Segurança de Senhas e Criptografia ---
SW-CORE-01(config)# enable secret SenhaForteEnable123!
SW-CORE-01(config)# service password-encryption

! --- 3. Mensagem de Alerta Legal (Banner MOTD) ---
SW-CORE-01(config)# banner motd #
====================================================================
  ACESSO RESTRITO! Apenas pessoal autorizado.
  Todas as conexões estão sendo monitoradas e auditadas.
====================================================================
#

! --- 4. Proteção de Acesso Físico (Porta Console) ---
SW-CORE-01(config)# line console 0
SW-CORE-01(config-line)# password SenhaConsoleForte123!
SW-CORE-01(config-line)# login
SW-CORE-01(config-line)# logging synchronous
SW-CORE-01(config-line)# exec-timeout 5 0
SW-CORE-01(config-line)# exit

! --- 5. Configuração de Acesso Remoto Seguro (SSH v2) ---
SW-CORE-01(config)# crypto key generate rsa modulus 2048
SW-CORE-01(config)# ip ssh version 2
SW-CORE-01(config)# username admin privilege 15 secret SenhaAdminSSH123!

SW-CORE-01(config)# line vty 0 15
SW-CORE-01(config-line)# login local
SW-CORE-01(config-line)# transport input ssh
SW-CORE-01(config-line)# exec-timeout 10 0
SW-CORE-01(config-line)# exit

! --- 6. Endereçamento IP na Interface de Gerenciamento (VLAN 1) ---
SW-CORE-01(config)# interface vlan 1
SW-CORE-01(config-if)# ip address 192.168.1.2 255.255.255.0
SW-CORE-01(config-if)# no shutdown
SW-CORE-01(config-if)# exit
SW-CORE-01(config)# ip default-gateway 192.168.1.1

! --- 7. Salvando as Configurações na NVRAM ---
SW-CORE-01(config)# end
SW-CORE-01# copy running-config startup-config
