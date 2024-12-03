# proxmox-ve
## Instalação, configurações e dicas.

## O Proxmox VE é um virtualizador de máquinas, assim como virtual box, vmware e hyper-v. Sua diferença encontra-se pela capacidade de criação de clusters e alta disponibilidade sendo uma ferramenta OpenSource.

1. Inicialmente precisamos baixar a iso do Proxmox VE em https://www.proxmox.com/en/downloads/proxmox-virtual-environment.
2. Após o download, iremos passar a iso para um pendrive, utilizando o rufus ou no caso de utilizar algum multiboot no pendrive basta copiar a iso para ele. (Em caso de servidor com gerenciador ILO/iDrac é possivel enviar a iso via rede também).
3. Depois do pendrive pronto ou a iso enviada para o servidor, devemos selecionar como inicialização.
4. A partir daqui, temos a tela do instalador já carregada.
![](https://github.com/sousa-97/proxmox-ve/blob/main/Captura%20de%20tela%202024-12-02%20073657.png?raw=true)
5. Agora iremos selecionar as configurações de disco e opções de RAID caso necessário.
### Dica - Eu normalmente utilizo btrfs para raids, o zfs permite replicação porém consome metade da Ram disponível e dependendo do hardware pode ser um problema! Em caso de um único disco, xfs pois trabalha melhor com grandes arquivos.
![](https://github.com/user-attachments/assets/41ee8f9c-3d77-44c7-810c-f01e73acfeed)
Opções de formatos e RAID's.
![](https://github.com/sousa-97/proxmox-ve/blob/main/Captura%20de%20tela%202024-12-02%20074537.png?raw=true)
6. Selecionaremos a região e definiremos senha e email para notificações.
![](https://github.com/sousa-97/proxmox-ve/blob/main/Captura%20de%20tela%202024-12-02%20074703.png?raw=true)
![](https://github.com/sousa-97/proxmox-ve/blob/main/Captura%20de%20tela%202024-12-02%20074713.png?raw=true)
7. Após, iremos configurar a rede. Selecionaremos a placa de rede principal que será responsável pelo acesso ao gerenciamento e também pode ser usado para Vms.
O hostname não precisa ser muito elaborado em caso de poucos servidores, mas criar nomenclaturas que façam sentido é uma boa prática e facilita o gerenciamento. Eu costumo iniciar com "pve" como sugere ou "pmx" e crio sequências, se terei mais de um servidor em cluster crio "pve1", "pve2", "pve3". Esse primerio nome antes do "." irá definir o nome no gerenciador.
![](https://github.com/sousa-97/proxmox-ve/blob/main/Captura%20de%20tela%202024-12-02%20074721.png?raw=true)
