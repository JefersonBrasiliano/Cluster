📘 Projeto Final – Cluster com Replicação de Banco de Dados e RAID
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
🔹 Configuração das VMs
Cada VM deve ser criada com:

Memória: 1024 MB.

💾 Discos:

NA01: 1 disco para SO + 6 discos de 10GB para RAID.

NA02: 1 disco para SO + 1 disco de 10GB para banco.

NC01, NC02, NC03: 1 disco para SO.

Rede: Adaptador interno (mesma rede).
<p></p>
🔹 Scripts de Configuração
Os scripts estão na pasta scripts/:

na01-slave.sh → Configura RAID, MySQL Slave, NFS e NIS.

na02-master.sh → Configura disco do banco e MySQL Master.
