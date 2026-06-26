# Lab 06 — inter-VLAN ROAS Config 

-------

## Topology
<img width="735" height="457" alt="image" src="https://github.com/user-attachments/assets/a6b7c7b0-ebba-459d-8fd3-75962959ae12" />

-------
# Problem

-PC1 can sends packet to PC3(10.0.0.3) while it is not able to communicate with other PCs.
<img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/70d4a0d0-3317-40f5-b63d-5c8a727a267f" />

-PC2 can sends packet to PC4(10.0.0.131) while it is not able to communicate with other PCs.
<img width="1918" height="1015" alt="image" src="https://github.com/user-attachments/assets/9d242e53-3dba-4d4a-8e79-e9319f5a3d1d" />

------
## Objective
To enable communication between different VLANs using a single physical router interface and cable. To maintain logical network segmentation and security while allowing necessary inter-VLAN traffic to pass through the router for policy control.

---

## Requirements

1. Ping between the PCs.  

2. Assign PC1 and PC3 to VLAN 13, and PC2 and PC4 to VLAN 24.

3. Create a trunk link between SW1 and SW2.  

4. Configure inter-VLAN routing by using subinterfaces on R1's G0/0 interface.  Use an address of 10.0.0.1/25 for VLAN 13 and 10.0.0.129/25 for VLAN 24.

5. Test connectivity by pinging between PCs.

---

## Configuration

<img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/b559cdee-e7b9-4c87-a75e-cbb7c61ff2b1" />
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/44c5265f-6b3c-4d16-8851-cf5056c8471f" />
<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/313f829b-eeda-4372-9c9c-e4ae3ab390e3" />


---

## Verification

- Testing connectivity from PC1.
 <img width="1918" height="1018" alt="image" src="https://github.com/user-attachments/assets/4f7391d6-39ae-4c4d-a151-128e0a441d57" />

- Testing connectivity from PC2.
 <img width="1918" height="1015" alt="image" src="https://github.com/user-attachments/assets/2849ccb4-2acc-4f9b-a1c5-bdc6497be88d" />

- Testing connectivity from PC3.
 <img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/866db1cf-d85e-4ee8-a170-481ce086f9de" />

- Testing connectivity from PC4.
 <img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/000d889b-b436-405a-8ee5-4bd1657db2c4" />


---

## Result

All PCs can now send packet to one another.

Configured successfully.
