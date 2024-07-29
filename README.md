## LINUX_COMMANDS


# VERIFICANDO INFORMAÇÕES DE USUÁRIOS LOGADOS REMOTAMENTE NO UBUNTU \ DEBIAN SERVER
### Lista os usuários atualmente logados no sistema
\`# sudo who -Ha`

# Exibe informações detalhadas sobre os usuários logados
\# sudo w

# Mostra apenas os nomes dos usuários logados
\# sudo users

# Lista as últimas tentativas de login, mostrando apenas os que ainda estão logados
\# sudo last -a | grep -i 'still logged in'

# Exibe conexões SSH ativas
\# sudo ss | grep -i ssh

# Mostra conexões estabelecidas com o daemon SSH
\# sudo netstat -tnpa | grep -i 'ESTABLISHED.*sshd'

# Lista processos relacionados ao daemon SSH
\# sudo ps -axfj | grep sshd

### VERIFICANDO AS INFORMAÇÕES DE LOG DE AUTENTICAÇÃO NO UBUNTU \ DEBIAN SERVER ###

# Filtra logs de autenticação para entradas relacionadas ao SSH
\# sudo cat /var/log/auth.log | grep ssh

# Filtra logs do sistema para entradas relacionadas ao SSH
\# sudo cat /var/log/syslog | grep ssh

### VERIFICANDO TENTATIVAS DE LOGIN FALHADAS ###

# Lista tentativas de login falhadas
sudo cat /var/log/auth.log | grep 'Failed password'

### MONITORANDO ALTERAÇÕES DE ARQUIVOS DE CONFIGURAÇÃO ###

# Mostra arquivos de configuração modificados recentemente
sudo find /etc -type f -mtime -1

### VERIFICANDO USO DE RECURSOS DO SISTEMA ###

# Exibe a utilização de CPU e memória pelos processos
top

# Exibe um resumo da utilização da memória
free -h

# Mostra a utilização de disco
df -h

# Verifica a utilização de inodes
df -i
Verificando Configurações de Firewall
bash
Copy code
# Lista as regras atuais do firewall
sudo iptables -L -v -n

# Verifica o status do firewall UFW (Uncomplicated Firewall)
sudo ufw status verbose
Verificando Integridade do Sistema
bash
Copy code
# Verifica a integridade de arquivos do sistema
sudo debsums -s
Monitorando Acessos Remotos
bash
Copy code
# Lista sessões remotas ativas
sudo ss -tuln

# Lista tentativas de login falhadas
sudo faillog -a
