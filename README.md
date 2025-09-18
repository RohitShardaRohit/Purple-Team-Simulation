# Purple-Team-Simulation
The objective of this project is to simulate a real-world attack from an attacker (Kali VM) to a victim (Ubuntu VM) and demonstrate detection using Wireshark
**What I did:**  
- Built two VMs (Kali attacker, Ubuntu victim) on a private VM network.  
- Ran discovery scans (`nmap -A`) and stealth reconnaissance (`nmap -sS`).  
- Performed a file transfer (SCP/SFTP) from attacker → victim to demonstrate exfiltration.  
- Captured results and recorded a short demo video showing the attack steps and outcomes.

**Why this is useful:**  
A compact, repeatable purple-team lab to rehearse detection, incident response steps, and to demonstrate attacker tradecraft for interviews or training.

---

## Repo contents
- `README.md` — this file (project summary).  
- `SETUP.md` — exact VM downloads, VirtualBox networking, and the commands you can run to reproduce the sim.  
- `DEMO.md` — a simple place to paste your demo video link and short transcript / timestamps.  
- (optional) `pcaps/`, `media/` — put any captured artifacts or screenshots here.

---

## License & ethics
Run this only on systems you own or explicitly have permission to test. Do not target third-party systems.
