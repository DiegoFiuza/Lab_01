# 🧠 Laboratório de Roteamento Linux com VirtualBox

## 📘 Descrição

Este projeto faz parte do meu aprendizado inicial em **DevOps**, com foco em redes e roteamento Linux.  
O objetivo foi configurar um ambiente com **3 máquinas virtuais** para simular o roteamento entre redes distintas.

---

## 🖥️ Estrutura do Lab

- **LinuxServer** → Ubuntu (Router)
- **client_1** → PopOS
- **client_2** → PopOS

<img width="718" height="314" alt="image" src="https://github.com/user-attachments/assets/008284a7-4d49-43c9-9a98-453459996860" />


---

## ⚙️ Configuração de Rede

### LinuxServer
- Adapter 1: NAT  
- Adapter 2: Rede Interna 1 (client_1)  
- Adapter 3: Rede Interna 2 (client_2)

### Clients
- `client_1`: Rede Interna 1 + NAT  
- `client_2`: Rede Interna 2 + NAT

🖼️ *[Inserir print das configurações de rede]*

---

## 🔍 Identificação dos IPs

Comando usado:
```bash
ip a
