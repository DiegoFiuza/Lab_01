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


---

## 🔍 Identificação dos IPs

Comando usado:
```bash
ip a
ping <ip_do_router>
ip r
tcpdump
# No client_1
ip route add <addr_Client_2> via <addr_Server_adapterVirtual_1>

# No client_2
ip route add <addr_Client_1> via <addr_Server_adapterVirtual_2>

<img width="1020" height="670" alt="image" src="https://github.com/user-attachments/assets/18aa4489-97dd-414b-862b-041d92e42161" />
<img width="799" height="502" alt="image" src="https://github.com/user-attachments/assets/b52e1281-c235-4362-8c3f-8827f5abab23" />
<img width="759" height="468" alt="image" src="https://github.com/user-attachments/assets/f0944eae-aa16-438d-a593-c9cd8531b748" />
```

## Feito teste de ping entre VM e Servidor para verificar se eles se comunicam
<img width="1110" height="542" alt="image" src="https://github.com/user-attachments/assets/5758d6c0-5af2-480f-aadb-52df07c86fea" />
<img width="1090" height="482" alt="image" src="https://github.com/user-attachments/assets/9ea34541-0fb1-4f45-ad4a-0ef9835533c6" />

🛠️ Criação de Rotas Estáticas
```
# No client_1
ip route add <addr_Client_2> via <addr_Server_adapterVirtual_1>

# No client_2
ip route add <addr_Client_1> via <addr_Server_adapterVirtual_2>
```
<img width="935" height="190" alt="image" src="https://github.com/user-attachments/assets/73595ef0-a8fa-494f-aba6-4180eb0f9ea8" />
<img width="1195" height="178" alt="image" src="https://github.com/user-attachments/assets/39af4e15-e4f4-4610-b503-e0090477afb3" />

🚦 Habilitando o IP Forward Temporariamente
```
Echo 1 > /proc/sys/net/ipv4/ip_forward
# Altere o valor de 0 para 1
```
📡 Teste Final com tcpdump
<img width="942" height="710" alt="image" src="https://github.com/user-attachments/assets/c7a5873d-43dd-468c-be3e-09c973ce0c63" />
<img width="1155" height="463" alt="image" src="https://github.com/user-attachments/assets/e7c89aea-97cb-4726-bbc1-e0d52ba5e867" />
<img width="1186" height="726" alt="image" src="https://github.com/user-attachments/assets/81315577-bb49-4ff8-b5a4-222f25a29c91" />





