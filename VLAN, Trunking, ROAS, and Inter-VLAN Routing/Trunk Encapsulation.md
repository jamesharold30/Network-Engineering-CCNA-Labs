# Lab 05 — VLAN Config Trunk Encapsulation


## Objective
To allow a single physical network link to carry traffic for multiple VLANs simultaneously.

---

## Topology
<img width="840" height="387" alt="image" src="https://github.com/user-attachments/assets/513451d7-d3e1-4c43-80c2-b15900d97cbb" />

---

## Requirements
1. Ping between the PCs to test connectivity.

2. Assign PC2 and PC3 to VLAN 2.

3. Create a trunk between SW1 and SW2.

4. Ping between the PCs to test connectivity.

---

## Configuration

```cisco
SW1 and SW2:

**enable** (entering previledge execmode).
**config t** (entering global execmode).
**ping ipadd** (used to test connectivity between PCs and sometimes used for troubleshooting)
**interface interfaceID** (to enter interface for configuration)
**switchport mode acc** (to turn an interface into access mode)
**switchport acc vlan** (to assign an interface into a VLAN)
**sw trunk encapsulation dot1q** (to allow trunking, commonly usable on some different device model like 3560-24PSwitch)
**sw mode trunk** (to make trunk able)
**ping ipadd** (used to test connectivity between PCs)

```

---

## Verification
- assigned PC2(10.0.0.2) via interface f0/3 to VLAN 2 and configured Trunk Encapsulation on SW1.
<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/484b7b86-c389-44a5-b519-1b773b77a2ce" />

- assigned PC3(10.0.0.3) to via interface f0/2 VLAN 2 and configured Trunk Encapsulation on SW2.
 <img width="1918" height="1015" alt="image" src="https://github.com/user-attachments/assets/2e2bbec6-b2a5-4242-9a66-9c7c95b55443" />

- Testing connectivity between PC2 and PC3. Also PC2 to PC1.
  <img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/f106f311-21cd-473f-9a72-2ef3db714885" />

- Testing connectivity between PC3 and PC2. Also PC3 to PC1.
<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/d24daf6b-d800-4e86-95b4-3f2bc61ee8dd" />

- Testing connectivity between PC1 and PC2. Also PC1 to PC3.
  <img width="1917" height="1023" alt="image" src="https://github.com/user-attachments/assets/13a9db19-953a-4184-8070-d2e16c1b5e1f" />


---

## Result
After all the configuration, I was expecting that PC2 and PC3 can communicate successfully and as expected, both PC2 and PC3 can send packets to each other.
On the other hand, PC1 was not able to communicate to both PC2 and PC3. It is because, PC1 is not on the same VLAN as PC2 and PC3.

On both Switches, I have also tried to configure the command "switchport mode trunk" without the Trunk Encapsulation and it was not able to activate the trunking.

I found out that the "switchport trunk encapsulation dot1q" is needed for some devices like 3560-24PS switch before I can actually able to configure "switchport mode trunk" sucessfully.

Since PCs that on the same VLAN can send packets to each other, I can say that the configurations including the Trunk Encapsulation is actually working.
so it is indeed successully configured.
