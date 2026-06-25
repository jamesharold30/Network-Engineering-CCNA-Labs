# Lab 01 — Basic Router Security Configuration

## Objective
Securing devices such as Router, using some Basic Router Security config.

---

## Topology
<img width="598" height="383" alt="image" src="https://github.com/user-attachments/assets/56881d6e-4411-4d1e-927c-86e6f84b2dd7" />

---

## Requirements
1. Connect R1 and R2 by their GigabitEthernet0/0 interfaces

2. Set the hostnames according to the network diagram (R1 and R2)

3. Set the enable password on each router to 'cisco'

4. View the password in the running configuration. 

5. Enable password encryption on each router

6. View the password in the running configuration. 

7. Disable password encryption on each router.

8. View the password in the running configuration. 

---

## Configuration

```cisco
R1 and R2:

**enable** (entering previledge execmode)
**config t** (entering global execmode)
**hostname R1** (setting up device's name)
**enable password cisco** (making it a password)
**service password-encryption** (password encryption)
**show running config** (view the current device's config settings or running config)
**no service password-encryption** (removing password encryption which only it affects the future passwords)
```

---

## Verification

<img width="1918" height="1025" alt="image" src="https://github.com/user-attachments/assets/a52c8464-3f6b-4e51-84f8-1e4e2f494615" />

<img width="1915" height="1013" alt="image" src="https://github.com/user-attachments/assets/032899a7-9303-4e5c-bb35-66d5b14296a5" />

<img width="1918" height="1030" alt="image" src="https://github.com/user-attachments/assets/d2f54c00-e40d-4084-8579-ec5f64046215" />

<img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/2245fe04-c39f-4fd6-8309-6832394768db" />

<img width="946" height="412" alt="image" src="https://github.com/user-attachments/assets/a4567e27-77f8-40fb-a8d5-516d53bd68d6" />


- viewed running config (step 4) and enable password is not encrypted by default.
- configure password encryption (step 5) and the password is finally encrypted with encryption type "7"
- Although "no service password-encryption" is configured, password is still encrypted. however, when a new or future passwords are configured,
 passwords automatically decrypted or let say "service password-encryption" is not automatically applied.

---

## Result
Successully configured.


# Lab 02 — Basic Router Security Configuration 2


## Objective
Securing devices such as Router, using some Basic Router Security config.

---

## Topology


---

## Requirements
1. Connect R1 and R2 by their GigabitEthernet0/0 interfaces

2. Set the hostnames according to the network diagram (R1 and R2)

3. Set the enable password on each router to 'cisco'

4. View the password in the running configuration. 

5. Enable password encryption on each router

6. View the password in the running configuration. 

7. Disable password encryption on each router.

8. View the password in the running configuration. 

---

## Configuration

```cisco
R1 and R2:

**enable** (entering previledge execmode)
**config t** (entering global execmode)
**hostname R1** (setting up device's name)
**enable password cisco** (making it a password)
**service password-encryption** (password encryption)
**show running config** (view the current device's config settings or running config)
**no service password-encryption** (removing password encryption which only it affects the future passwords)

```

---

## Verification

```
<img width="688" height="562" alt="image" src="https://github.com/user-attachments/assets/a2a3cdde-e3e1-4b90-8ad1-333adceb5046" />

- viewed running config (step 4) and enable password is not encrypted by default.
- configure password encryption (step 5) and the password is finally encrypted with encryption type "7"
- Although "no service password-encryption" is configured, password is still encrypted. however, when a new or future passwords are configured,
 passwords automatically decrypted or let say "service password-encryption" is not automatically applied.

---

## Result
Successully configured.
