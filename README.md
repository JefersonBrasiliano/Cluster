📘 Cluster com Replicação de Banco de Dados e RAID

Projeto desenvolvido a partir da disciplina Arquitetura de Alto Desempenho para Banco de Dados (UNICAMP), ministrada pelo Prof. José Luís Zem.
<p></p>

🔹 Visão Geral
Este projeto implementa um cluster de computadores com:

Replicação de banco de dados MySQL (Master/Slave).

Armazenamento redundante via RAID 1.

Serviços adicionais no Slave: NFS (compartilhamento de arquivos) e NIS (autenticação de usuários).

Nós de computação (NC01, NC02, NC03) dedicados apenas a consultas (SELECT).
<p></p>
🔹 Arquitetura
<p></p>

<img width="1044" height="517" alt="image" src="https://github.com/user-attachments/assets/684e9e67-a395-4d6a-8f04-8393387a59d0" />

<p></p>
🖥️ NA02 (Master)

Banco de dados principal.

Aceita operações de escrita (INSERT, UPDATE, DELETE).
<p></p>
🖥️ NA01 (Slave)

Replica automaticamente o banco do Master.

Executa serviços de NFS e NIS.

<p></p>
🖥️ NC01, NC02, NC03

Apenas consultas (SELECT).

Sincronização via FLUSH TABLES.
<p></p>
🔹 Pré-requisitos
VirtualBox instalado.

Linux (Slax ou Debian/Ubuntu) em cada VM.

MySQL/MariaDB instalado.

Pacotes: mdadm, nfs-kernel-server, nis.
<p></p>
🔹 Configuração das VMs:

Memória: 1024 MB.

💾 Discos:

NA01: 1 disco para SO + 6 discos de 10GB para RAID.

NA02: 1 disco para SO + 1 disco de 10GB para banco.

NC01, NC02, NC03: 1 disco para SO.

Rede: Adaptador interno (mesma rede).
<p></p>

Para baixar o appliance, [clique aqui](https://1drv.ms/f/c/80560f64d3055d84/IgAhnevmR7ONToT5f8dU0UWXAZBIXdgC8KF19vKucrFudpg?e=5hlFSG)
<img width="1498" height="126" alt="image" src="https://github.com/user-attachments/assets/352bca55-1319-4528-9b7f-8ccfcc7153c4" />
