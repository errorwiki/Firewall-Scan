**FirewallScan**

**Task:** Setting Up and Using a Firewall on Linux (UFW)

This repository contains my work on configuring a firewall. The objective was to set up UFW (Uncomplicated FireWall) on a Kali Linux system, block inbound traffic on port 23 (Telnet), test the rule, and then restore the original firewall state.

<img width="860" height="887" alt="image" src="https://github.com/user-attachments/assets/e4f26761-18c2-4c91-92a6-33c60433d4f5" />


### Steps Taken

1. **Checked Existing Firewall Rules:**
   - Used the commands `sudo ufw status numbered` and `sudo ufw status verbose` to list the active rules.

2. **Enabled UFW (If Not Already Active):**
   - Verified that UFW was active with the default policy set to deny incoming connections and allow outgoing connections.

3. **Added a Rule to Block Port 23 (Telnet):**
   - Command used:
     ```
     sudo ufw deny 23
     ```

4. **Allowed SSH (Port 22) to Ensure Secure Access:**
   - Command used:
     ```
     sudo ufw allow 22
     ```

5. **Verified the Firewall Rules After Adding the Block:**
   - Confirmed that the DENY rule for port 23 was present.

6. **Tested the Block Rule:**
   - Attempted to connect to port 23 using:
     ```
     telnet localhost 23
     ```
   - The connection failed as expected, confirming that the block was effective.

7. **Removed the Block Rule to Restore the Original State:**
   - Command used:
     ```
     sudo ufw delete deny 23
     ```

8. **Confirmed Final Firewall Rules to Ensure Cleanup:**
   - Used `sudo ufw status numbered` to verify that the block on port 23 had been removed.

### Evidence

Screenshots of the following are included in the firewall folder:
- Initial firewall rules
- Rules after blocking port 23
- Telnet test showing connection refused
- Final rules after removing the block

### Outcome

Successfully configured and managed firewall rules on Linux using UFW. 
Demonstrated the ability to block and unblock specific ports and verified the firewall's behavior through testing.
