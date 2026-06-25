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

**enable** (entering priviledge execmode)
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
<img width="557" height="381" alt="image" src="https://github.com/user-attachments/assets/ed41ef7f-c8a5-4727-8f66-1ff5e0f35c7d" />

---

## Requirements
1. Connect the two routers by their GigabitEthernet0/0 interfaces

2. Set the hostname of each router according to the network diagram (R1 and R2)

3. Set the enable password of each router to 'cisco'

4. Set the enable secret of each router to 'ccna'

5. Exit back to exec mode and try to enter privileged exec mode. 

6. View the running configuration.  

7. Enable password encryption on the router, and view the running configuration.

8. Save the configuration and reload the router to confirm.

---

## Configuration

```cisco
R1 and R2:

**enable** (entering previledge execmode).
**config t** (entering global execmode).
**hostname R1** (setting up device's name).
**enable password cisco** (making it a password).
**show running config** (view the current device's config settings or running config).
**enable secret** (make an encrypted password with encryption type "5" by default).
**service password-encryption** (password encryption).
**show running config** (view the current device's config settings or running config).
**service password-encryption** (It only encrypts the configured "enable password" command).
**write** (to save the configuration)
**reload** (to reload cli)
**show startup-config** (to confirm that the previous configuration is saved)

```

---

## Verification

<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/7d15c55f-2081-4b9c-97ff-d5033f89fe56" />

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/720eed87-c862-4f87-8721-1c6d8a7ec604" />

<img width="391" height="222" alt="image" src="https://github.com/user-attachments/assets/53c4a06d-5f8c-46d2-8dbc-90670d092fbd" />

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/edece25d-e55f-42fe-b108-c48f83ccd58d" />

- exit the global execmode using "exit" command twice until reach outside of user execmode, and tried to re-enter the priviledge exec mode. as expected, It uses the "enable secret" command as it is more secure than "enable password" command.
- viewed running config (step 7) and found out that enable secret is encrypted while the other command "enable password" is not encrypted by default.
- I have learned that "service password-encryption" command only encrypts "enable password" configured.
- So what was changed when i configured service password-encryption was that "enable password" is now encrypted.
---

## Result
Successully configured.

# Lab 03 — Basic Router Security Configuration 3


## Objective
Securing devices such as Router, using some Basic Router Security config.

---

## Topology
<img width="568" height="261" alt="image" src="https://github.com/user-attachments/assets/4a5000ea-5f89-4fb5-a534-be2c1e44fbed" />

---

## Requirements
1. Connect PC1's RS-232 port to R1's console port.

2. Use the console connection to configure the router from PC1.  Change the hostname to R1.

3. Set the enable secret of R1 to 'cisco'.

4. Set the console password of R1 to 'ccna', and make it required to connect to R1 by the console port.  Check the runing configuration.  Is the password encrypted?

5. Enable password encryption on R1.  Verify by checking the running configuration, and then save your configurations.
---

## Configuration

```cisco
R1:

**enable** (entering previledge execmode)
**config t** (entering global execmode)
**hostname R1** (setting up device's name)
**enable secret** (make an encrypted password with encryption type "5" by default).
**line console 0** (to enter and configure console)
**password password** (to configure a password for console)
**login** (to make the password configured required to connect R1 by the console port)
**show running config** (view the current device's config settings or running config)
**service password-encryption** (It only encrypts the configured "enable password" command).
**write** (to save the configuration)
**reload** (to reload cli)
**show startup-config** (to confirm that the previous configuration is saved)

```

---

## Verification

<img width="1918" height="1008" alt="image" src="https://github.com/user-attachments/assets/f1bea381-f970-480e-a2c4-0ea4416ae008" />
<img width="386" height="80" alt="image" src="https://github.com/user-attachments/assets/6e3b8536-0005-4586-9280-d2f82db96fbf" />
<img width="387" height="83" alt="image" src="https://github.com/user-attachments/assets/32b47865-585d-4183-ad63-349e9b0bc36a" />
<img width="312" height="73" alt="image" src="https://github.com/user-attachments/assets/48b9ac49-0480-4dad-86de-146c7dd61e33" />
<img width="953" height="353" alt="image" src="https://github.com/user-attachments/assets/27850c35-be11-4b55-be6c-39ae1087f982" />
<img width="527" height="131" alt="image" src="https://github.com/user-attachments/assets/fc4bea8e-1705-4db0-b6a1-056678528f0c" />

---

## Result
Successully configured.
