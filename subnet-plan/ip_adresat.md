# Plani i IP Adresave — Rrjeta SOHO

## Shkolla "Isa Boletini"

### Lënda: Rrjetat Kompjuterike 2025/26 — Projekti III

---

## Hapësira kryesore e adresimit

| Detaj | Vlera |
|---|---|
| Blloku kryesor | `192.168.0.0/16` |
| Subnet mask për VLAN-et | `255.255.255.0` (`/24`) |
| Numri i subnet-eve të planifikuara | 5 |
| Lloji i adresimit | Statik |

---

## VLAN-et dhe subnet-et

| VLAN ID | Emri | Subnet | Gateway | Hostet max | Pajisjet |
|---|---|---|---|---|---|
| VLAN 10 | PC_Network | `192.168.10.0/24` | `192.168.10.1` | 254 | 12 PC + Printer |
| VLAN 20 | Laptop_Network | `192.168.20.0/24` | `192.168.20.1` | 254 | 8 Laptopë + Access Points + Printer |
| VLAN 30 | Server_Network | `192.168.30.0/24` | `192.168.30.1` | 254 | Web Server + DNS Server |
| VLAN 40 | VoIP_Network | `192.168.40.0/24` | `192.168.40.1` | 254 | 4 Telefona IP |
| VLAN 50 | Management | `192.168.50.0/24` | `192.168.50.1` | 254 | IoT + Smart Devices + Network Controller |

---

## VLAN 10 — PC Network (`192.168.10.0/24`)

**Përgjegjës për PC-të: End Devices & Servers**

| Pajisja | IP Adresa | Subnet Mask | Default Gateway | DNS Server | Switch Port |
|---|---|---|---|---|---|
| PC-1 | `192.168.10.2` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/3 |
| PC-2 | `192.168.10.3` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/4 |
| PC-3 | `192.168.10.4` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/5 |
| PC-4 | `192.168.10.5` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/6 |
| PC-5 | `192.168.10.6` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/7 |
| PC-6 | `192.168.10.7` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/8 |
| PC-7 | `192.168.10.8` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/9 |
| PC-8 | `192.168.10.9` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/10 |
| PC-9 | `192.168.10.10` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/11 |
| PC-10 | `192.168.10.11` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/12 |
| PC-11 | `192.168.10.12` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/13 |
| PC-12 | `192.168.10.13` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | SW1 Fa0/14 |
| Printer-1 | `192.168.10.14` | `255.255.255.0` | `192.168.10.1` | `192.168.30.3` | Sipas konfigurimit të grupit |

---

## VLAN 20 — Laptop Network (`192.168.20.0/24`)

**Përgjegjës për laptopët: End Devices & Servers**  
**Përgjegjës për Access Points: Wireless, VoIP & Security**

| Pajisja | IP Adresa | Subnet Mask | Default Gateway | DNS Server | Switch Port |
|---|---|---|---|---|---|
| Laptop-1 | `192.168.20.2` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/2 |
| Laptop-2 | `192.168.20.3` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/3 |
| Laptop-3 | `192.168.20.4` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/4 |
| Laptop-4 | `192.168.20.5` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/5 |
| Laptop-5 | `192.168.20.6` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/6 |
| Laptop-6 | `192.168.20.7` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/7 |
| Laptop-7 | `192.168.20.8` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/8 |
| Laptop-8 | `192.168.20.9` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | SW2 Fa0/9 |
| Access Point-1 | `192.168.20.10` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | Sipas konfigurimit të grupit |
| Access Point-2 | `192.168.20.11` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | Sipas konfigurimit të grupit |
| Printer-2 | `192.168.20.12` | `255.255.255.0` | `192.168.20.1` | `192.168.30.3` | Sipas konfigurimit të grupit |

---

## VLAN 30 — Server Network (`192.168.30.0/24`)

**Përgjegjës: End Devices & Servers**

| Pajisja | IP Adresa | Subnet Mask | Default Gateway | DNS Server | Shërbimi | Switch Port |
|---|---|---|---|---|---|---|
| Web Server | `192.168.30.2` | `255.255.255.0` | `192.168.30.1` | `192.168.30.3` | HTTP — port 80 | SW3 Fa0/2 |
| DNS Server | `192.168.30.3` | `255.255.255.0` | `192.168.30.1` | `192.168.30.3` | DNS — port 53 | SW3 Fa0/3 |

### DNS Records

| Emri | Tipi | IP Adresa |
|---|---|---|
| `www.shkolla.local` | A Record | `192.168.30.2` |
| `shkolla.local` | A Record | `192.168.30.2` |

---

## VLAN 40 — VoIP Network (`192.168.40.0/24`)

**Përgjegjës: Wireless, VoIP & Security**

| Pajisja | IP Adresa | Subnet Mask | Default Gateway | DNS Server | Switch Port |
|---|---|---|---|---|---|
| Telefon IP-1 | `192.168.40.2` | `255.255.255.0` | `192.168.40.1` | `192.168.30.3` | Sipas konfigurimit të grupit |
| Telefon IP-2 | `192.168.40.3` | `255.255.255.0` | `192.168.40.1` | `192.168.30.3` | Sipas konfigurimit të grupit |
| Telefon IP-3 | `192.168.40.4` | `255.255.255.0` | `192.168.40.1` | `192.168.30.3` | Sipas konfigurimit të grupit |
| Telefon IP-4 | `192.168.40.5` | `255.255.255.0` | `192.168.40.1` | `192.168.30.3` | Sipas konfigurimit të grupit |

---

## VLAN 50 — Management (`192.168.50.0/24`)

**Përgjegjës: Smart Devices, IoT & Dokumentimi**

| Pajisja | IP Adresa | Subnet Mask | Default Gateway | DNS Server | Lidhja |
|---|---|---|---|---|---|
| Smart Device-1 | `192.168.50.2` | `255.255.255.0` | `192.168.50.1` | `192.168.30.3` | Wireless |
| Smart Device-2 | `192.168.50.3` | `255.255.255.0` | `192.168.50.1` | `192.168.30.3` | Wireless |
| Smart Device-3 | `192.168.50.4` | `255.255.255.0` | `192.168.50.1` | `192.168.30.3` | Wireless |
| IoT Pajisje | `192.168.50.5` | `255.255.255.0` | `192.168.50.1` | `192.168.30.3` | Wireless |
| Network Controller | `192.168.50.6` | `255.255.255.0` | `192.168.50.1` | `192.168.30.3` | Sipas konfigurimit të grupit |

---

## Gateway-t për inter-VLAN routing

**Përgjegjës: Network Infrastructure**

Këto gateway duhet të konfigurohen nga pjesa e Network Infrastructure në routerin kryesor. Pajisjet fundore janë konfiguruar duke përdorur këto gateway.

| VLAN | Gateway | Përshkrimi |
|---|---|---|
| VLAN 10 | `192.168.10.1` | Gateway për PC Network |
| VLAN 20 | `192.168.20.1` | Gateway për Laptop Network |
| VLAN 30 | `192.168.30.1` | Gateway për Server Network |
| VLAN 40 | `192.168.40.1` | Gateway për VoIP Network |
| VLAN 50 | `192.168.50.1` | Gateway për Management Network |

> Shënim: Mënyra e konfigurimit të inter-VLAN routing, p.sh. me router-on-a-stick ose me lidhje të veçanta fizike, përcaktohet nga pjesa Network Infrastructure. Ky dokument përcakton gateway-t dhe subnet-et që duhet të përputhen me konfigurimin final.

---

## Lidhjet e propozuara ndërmjet switch-ave dhe routerit

**Përgjegjës: Network Infrastructure**

Kjo pjesë është plan i propozuar dhe mund të ndryshohet nga personi përgjegjës për routing dhe topologji.

| Nga | Porta | Në | Porta | Lloji i kabllos |
|---|---|---|---|---|
| SW1 | Fa0/24 | R1 | Sipas konfigurimit final | Straight-Through |
| SW2 | Fa0/24 | R1 | Sipas konfigurimit final | Straight-Through |
| SW3 | Fa0/24 | R1 | Sipas konfigurimit final | Straight-Through |

---

## Përmbledhje — Numri i pajisjeve

| Kategoria | Sasia | VLAN | Përgjegjës |
|---|---:|---|---|
| PC | 12 | VLAN 10 | End Devices & Servers |
| Laptop | 8 | VLAN 20 | End Devices & Servers |
| Web Server | 1 | VLAN 30 | End Devices & Servers |
| DNS Server | 1 | VLAN 30 | End Devices & Servers |
| Printer | 2 | VLAN 10, VLAN 20 | Smart Devices, IoT & Dokumentimi |
| Access Point | 2 | VLAN 20 | Wireless, VoIP & Security |
| Telefona IP | 4 | VLAN 40 | Wireless, VoIP & Security |
| Smart Devices | 3 | VLAN 50 | Smart Devices, IoT & Dokumentimi |
| IoT | 1 | VLAN 50 | Smart Devices, IoT & Dokumentimi |
| Network Controller | 1 | VLAN 50 | Smart Devices, IoT & Dokumentimi |
| **Totali pajisje fundore** | **35** | — | — |

---

## Shënime

- Të gjitha pajisjet përdorin IP adresa statike.
- DNS Server është `192.168.30.3`.
- Web Server është `192.168.30.2`.
- Emri `www.shkolla.local` lidhet me Web Server-in.
- Inter-VLAN routing bëhet nga pjesa Network Infrastructure dhe duhet të përputhet me gateway-t e përcaktuara në këtë plan.
- Pajisjet wireless, smart devices dhe IoT duhet të konfigurohen sipas VLAN-it dhe subnet-it të përcaktuar nga grupi.