# 🏫 Rrjeta Kompjuterike e Shkollës Fillore "Isa Boletini"

**Lënda:** Rrjetat Kompjuterike 2025/26  
**Grupi:** Gr. 17  
**Anëtarët:** Altin Mulaj | Genta Gara | Gerti Parduzi | Genti Kafexhiu  
**Profesori:** Prof. Dr. Blerim REXHA | PhD Cand. Rrezearta THAQI

---

## 📁 Struktura e Repo-s

```
soho-network/
├── README.md
├── .gitignore
├── packet-tracer/
│   └── shkolla_IsaBoletini.pkt        ← Fajlli kryesor i Packet Tracer
├── docs/
│   ├── dokumentimi.docx               ← Dokumentimi Word
│   └── dokumentimi.pdf                ← Dokumentimi PDF
└── subnet-plan/
    └── ip_adresat.md                  ← Plani i IP adresave
```

---

## 🌐 Topologjia e Rrjetës

Rrjeta ndahet në **5 VLAN-e** të pavarura:

| VLAN | Emri | Subnet | Gateway | Pajisjet |
|------|------|--------|---------|----------|
| VLAN 10 | PC Network | 192.168.10.0/24 | 192.168.10.1 | 12 PC + Printer |
| VLAN 20 | Laptop Network | 192.168.20.0/24 | 192.168.20.1 | 8 Laptop + 2 AP + Printer |
| VLAN 30 | Server Network | 192.168.30.0/24 | 192.168.30.1 | Web Server + DNS Server |
| VLAN 40 | VoIP Network | 192.168.40.0/24 | 192.168.40.1 | 4 IP Phone |
| VLAN 50 | Management | 192.168.50.0/24 | 192.168.50.1 | Smart Devices + IoT + NC |

---

## ⚙️ Pajisjet e Rrjetës

| Pajisja | Modeli | Sasia | Roli |
|---------|--------|-------|------|
| Router Kryesor | Cisco 2911 (R1) | 1 | Inter-VLAN Routing VLAN 10/20/30 |
| Router Wireless | Cisco 2911 (R2) | 1 | Gateway VLAN 40/50 |
| Router ISP | Cisco 2911 (R3) | 1 | Lidhja me Internet |
| Switch | Cisco 2960 (SW1-SW4) | 4 | Një për çdo VLAN |
| Hub | Hub-PT (HUB1) | 1 | Lidhje shtesë |
| Cell Tower | Cell Tower | 2 | Komunikim celular |
| Home Gateway | DLC100 | 1 | Gateway shtëpiak |
| Firewall | ASA 5505 | 1 | Siguria e rrjetës |

---

## 🖥️ Pajisjet Fundore

| Pajisja | Sasia | VLAN | Përgjegjësi |
|---------|-------|------|-------------|
| PC | 12 | VLAN 10 | Personi 2 |
| Laptop | 8 | VLAN 20 | Personi 2 |
| Web Server | 1 | VLAN 30 | Personi 2 |
| DNS Server | 1 | VLAN 30 | Personi 2 |
| Printer | 2 | VLAN 10, 20 | Personi 4 |
| IP Phone | 4 | VLAN 40 | Personi 3 |
| Access Point | 2 | VLAN 20 | Personi 3 |
| Smart Device | 3 | VLAN 50 | Personi 4 |
| IoT Pajisje | 1 | VLAN 50 | Personi 4 |
| Network Controller | 1 | VLAN 50 | Personi 4 |
| **TOTALI** | **35** | — | — |

---

## 🔌 Konfigurimi i Routerëve

### R1 (Kryesor)
| Interface | IP Adresa | Rrjeta |
|-----------|-----------|--------|
| GigabitEthernet0/0 | 192.168.10.1 | VLAN 10 |
| GigabitEthernet0/1 | 192.168.20.1 | VLAN 20 |
| GigabitEthernet0/2 | 192.168.30.1 | VLAN 30 |
| Serial0/3/1 | 192.168.40.1 | Lidhja R1↔R2 |

### R2 (Wireless)
| Interface | IP Adresa | Rrjeta |
|-----------|-----------|--------|
| Serial0/3/0 | 192.168.40.2 | Lidhja R2↔R1 |
| GigabitEthernet0/0 | 192.168.50.1 | VLAN 50 |

### Static Routing
**R1:**
```
ip route 192.168.40.0 255.255.255.0 Serial0/3/1
ip route 192.168.50.0 255.255.255.0 192.168.40.2
```
**R2:**
```
ip route 192.168.10.0 255.255.255.0 192.168.40.1
ip route 192.168.20.0 255.255.255.0 192.168.40.1
ip route 192.168.30.0 255.255.255.0 192.168.40.1
```

---

## 📋 IP Adresat — Përmbledhje

### VLAN 10 — PC Network
| Pajisja | IP | Gateway | DNS |
|---------|----|---------|-----|
| PC-1 deri PC-12 | 192.168.10.2 — .13 | 192.168.10.1 | 192.168.30.3 |
| Printer-1 | 192.168.10.14 | 192.168.10.1 | 192.168.30.3 |

### VLAN 20 — Laptop Network
| Pajisja | IP | Gateway | DNS |
|---------|----|---------|-----|
| Laptop-1 deri 8 | 192.168.20.2 — .9 | 192.168.20.1 | 192.168.30.3 |
| Access Point-1 | 192.168.20.10 | 192.168.20.1 | 192.168.30.3 |
| Access Point-2 | 192.168.20.11 | 192.168.20.1 | 192.168.30.3 |
| Printer-2 | 192.168.20.12 | 192.168.20.1 | 192.168.30.3 |

### VLAN 30 — Server Network
| Pajisja | IP | Shërbimi |
|---------|----|---------|
| Web Server | 192.168.30.2 | HTTP port 80 |
| DNS Server | 192.168.30.3 | DNS port 53 |

### VLAN 40 — VoIP
| Pajisja | IP | Gateway |
|---------|----|---------|
| IP Phone-0 deri 3 | 192.168.40.2 — .5 | 192.168.40.1 |

### VLAN 50 — Management
| Pajisja | IP | Gateway |
|---------|----|---------|
| Smart Device-1/2/3 | 192.168.50.2 — .4 | 192.168.50.1 |
| IoT Pajisje | 192.168.50.5 | 192.168.50.1 |
| Network Controller | 192.168.50.6 | 192.168.50.1 |

---

## 👥 Ndarja e Punës

| Anëtari | Pjesa | Pajisjet |
|---------|-------|----------|
| **Altin Mulaj** | Network Infrastructure | R1, R2, R3, SW1-SW4, HUB1, IP Addressing, Routing |
| **Genta Gara** | End Devices & Serverët | 12 PC, 8 Laptop, Web Server, DNS Server |
| **Gerti Parduzi** | Wireless, VoIP & Security | 2 AP, 4 IP Phone, Firewall, 2 Cell Tower, Home Gateway |
| **Genti Kafexhiu** | Smart/IoT & Dokumentimi | 3 Smart Device, 1 IoT, 1 NC, 2 Printer, Dokumentimi |

---

## ✅ Testimi

| Testi | Rezultati |
|-------|-----------|
| R1 → VLAN 10 (192.168.10.1) | ✅ 100% |
| R1 → VLAN 20 (192.168.20.1) | ✅ 100% |
| R1 → VLAN 30 (192.168.30.1) | ✅ 100% |
| R1 → R2 Serial (192.168.40.2) | ✅ 100% |
| R1 → VLAN 50 (192.168.50.1) | ✅ 100% |

---

```

**Lajmëro grupin në WhatsApp para dhe pas punës!**
