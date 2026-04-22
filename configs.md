# ⚙️ Router Configurations

Full CLI configurations for all 4 routers in the enterprise network topology, implemented using GNS3 with OSPF dynamic routing.

---

## 🔧 R1

```
conf t
int f0/0
 ip address 178.15.32.1 255.255.240.0
 no shutdown
int s1/2
 ip address 178.15.80.1 255.255.240.0
 ip ospf cost 1
 no shutdown
int s1/1
 ip address 178.15.96.1 255.255.240.0
 ip ospf cost 2
 no shutdown
int s1/3
 ip address 178.15.112.1 255.255.240.0
 ip ospf cost 2
 no shutdown
exit
router ospf 1
 network 178.15.32.0 0.0.15.255 area 0
 network 178.15.80.0 0.0.15.255 area 0
 network 178.15.96.0 0.0.15.255 area 0
 network 178.15.112.0 0.0.15.255 area 0
exit
end
write memory
```

---

## 🔧 R2

```
conf t
int f0/0
 ip address 178.15.64.1 255.255.240.0
 no shutdown
int s1/2
 ip address 178.15.80.2 255.255.240.0
 ip ospf cost 1
 no shutdown
int s1/3
 ip address 178.15.128.1 255.255.240.0
 ip ospf cost 5
 no shutdown
int s1/1
 ip address 178.15.144.1 255.255.240.0
 ip ospf cost 7
 no shutdown
exit
router ospf 1
 network 178.15.64.0 0.0.15.255 area 0
 network 178.15.80.0 0.0.15.255 area 0
 network 178.15.128.0 0.0.15.255 area 0
 network 178.15.144.0 0.0.15.255 area 0
exit
end
write memory
```

---

## 🔧 R3

```
conf t
int f0/0
 ip address 178.15.16.1 255.255.240.0
 no shutdown
int s1/1
 ip address 178.15.96.2 255.255.240.0
 ip ospf cost 2
 no shutdown
int s1/3
 ip address 178.15.128.2 255.255.240.0
 ip ospf cost 5
 no shutdown
int s1/2
 ip address 178.15.160.1 255.255.240.0
 ip ospf cost 3
 no shutdown
exit
router ospf 1
 network 178.15.16.0 0.0.15.255 area 0
 network 178.15.96.0 0.0.15.255 area 0
 network 178.15.128.0 0.0.15.255 area 0
 network 178.15.160.0 0.0.15.255 area 0
exit
end
write memory
```

---

## 🔧 R4

```
conf t
int f0/0
 ip address 178.15.48.1 255.255.240.0
 no shutdown
int s1/3
 ip address 178.15.112.2 255.255.240.0
 ip ospf cost 2
 no shutdown
int s1/1
 ip address 178.15.144.2 255.255.240.0
 ip ospf cost 7
 no shutdown
int s1/2
 ip address 178.15.160.2 255.255.240.0
 ip ospf cost 3
 no shutdown
exit
router ospf 1
 network 178.15.48.0 0.0.15.255 area 0
 network 178.15.112.0 0.0.15.255 area 0
 network 178.15.144.0 0.0.15.255 area 0
 network 178.15.160.0 0.0.15.255 area 0
exit
end
write memory
```

---

## 🌐 IP Addressing Summary

| Router | Interface | IP Address       | Subnet Mask     | OSPF Cost |
|--------|-----------|------------------|-----------------|-----------|
| R1     | f0/0      | 178.15.32.1      | 255.255.240.0   | -         |
| R1     | s1/2      | 178.15.80.1      | 255.255.240.0   | 1         |
| R1     | s1/1      | 178.15.96.1      | 255.255.240.0   | 2         |
| R1     | s1/3      | 178.15.112.1     | 255.255.240.0   | 2         |
| R2     | f0/0      | 178.15.64.1      | 255.255.240.0   | -         |
| R2     | s1/2      | 178.15.80.2      | 255.255.240.0   | 1         |
| R2     | s1/3      | 178.15.128.1     | 255.255.240.0   | 5         |
| R2     | s1/1      | 178.15.144.1     | 255.255.240.0   | 7         |
| R3     | f0/0      | 178.15.16.1      | 255.255.240.0   | -         |
| R3     | s1/1      | 178.15.96.2      | 255.255.240.0   | 2         |
| R3     | s1/3      | 178.15.128.2     | 255.255.240.0   | 5         |
| R3     | s1/2      | 178.15.160.1     | 255.255.240.0   | 3         |
| R4     | f0/0      | 178.15.48.1      | 255.255.240.0   | -         |
| R4     | s1/3      | 178.15.112.2     | 255.255.240.0   | 2         |
| R4     | s1/1      | 178.15.144.2     | 255.255.240.0   | 7         |
| R4     | s1/2      | 178.15.160.2     | 255.255.240.0   | 3         |


