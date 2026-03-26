# SSH Brute Force Detection Lab

**Overview**

This project demonstrates a simple cybersecurity lab where an SSH brute force attack was simulated and monitored using Wazuh. The attacker was automatically blocked using fail2ban after repeated failed login attempts.

**Lab Setup**

Kali Linux – attacker machine
Ubuntu – target machine (SSH + Wazuh agent)
Wazuh Manager – monitoring and alert detection

**Attack**

A brute force attack was performed using Hydra:

```bash
hydra -l agents -P rockyou.txt ssh://192.168.56.104
```

The correct credentials were discovered:

Username: agents
Password: 1539

**Detection (Wazuh)**

Wazuh detected the attack and generated alerts including:

SSH authentication failures
Brute force activity
Password guessing
Valid account login

**Response (fail2ban)**

fail2ban automatically blocked the attacker IP after multiple failed login attempts, preventing further access.

**Key Takeaways**

Simulated a real brute force attack
Monitored activity using Wazuh SIEM
Analyzed security alerts
Implemented automated blocking with fail2ban

**Summary**

This lab demonstrates a complete security workflow:

Attack → Detection → Response
