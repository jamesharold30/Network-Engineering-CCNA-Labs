# Lab 04 — VLAN Configuration

## Objective
To logically segment a single physical network into multiple, isolated virtual networks.

---

## Topology
<img width="598" height="383" alt="image" src="https://github.com/user-attachments/assets/56881d6e-4411-4d1e-927c-86e6f84b2dd7" />

---

## Requirements
1. Ping between the computers to test connectivity.

2. Assign PC1 and PC3 to VLAN1, and PC2 and PC4 to VLAN2.

3. Attempt to ping between PC1 and PC3, and then PC2 and PC4.  

4. Configure the interfaces connecting SW1 and SW2 as trunk interfaces.

5. Ping between the computers again. 

---

## Configuration

```cisco
R1 and R2:

**enable** (entering priviledge execmode)
**config t** (entering global execmode)
**interface interfaceID** (Entering an interface to configure)
**switchport mode acc** (to make port in access mode)
**switchport acc vlan** (to assign an interface into a VLAN)
**switchport mode trunk** (to make trunking able)
```

---

## Verification

-On SW1 I configure VLAN with assigning PC2 to Vlan 2 and for VLAN 1 on the other hand PC1 was not needed to configure as all interfaces are already assigned in the Native VLAN which is the VLAN 1. also I onfigure Trunk.
<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/ee16fd55-bd27-4106-8af0-c75e0363ebbb" />

-On SW2 I configure VLAN with assigning PC4 to Vlan 2 and for VLAN 1 on the other hand PC3 was not needed to configure as all interfaces are already assigned in the Native VLAN which is the VLAN 1. also I configure Trunk.
<img width="1913" height="1018" alt="image" src="https://github.com/user-attachments/assets/e7b4938b-475e-4440-b845-c56418f20c25" />

- Testing the connectivity from VLAN 1's PC1 (10.0.0.1)
  <img width="1918" height="1026" alt="image" src="https://github.com/user-attachments/assets/31f105e0-9a35-49b5-b010-2e6c0c4900d9" />
  
- Testing the connectivity from VLAN 2's PC2 (10.0.0.2)
  <img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/9eba614b-2c97-4d81-bcfd-07f3323457cb" />


---

## Result

After all VLANs configured, PC1 to PC2 connection was not successful. PC2 to PC3 neither.
As expected, VLAN 1's PC1 and PC3 can send packets to each other successfully. Also PC2 and PC4 (VLAN 2). 
Successully configured.
