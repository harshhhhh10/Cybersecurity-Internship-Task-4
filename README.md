# Task 4: Windows Firewall Configuration and Testing

 Objective
Configure and test basic firewall rules to block and allow network traffic.

 Task Summary

Successfully created an inbound firewall rule to block port 23 (Telnet) and tested it to confirm the rule works.

# Rule Created: Block Telnet Port 23

Configuration:
- Type: Inbound Rule
- Protocol: TCP
- Port: 23
- Action: Block the connection
- Profiles: Domain, Private, Public
- Status: Enabled 

Description: Blocks inbound connections on port 23 (Telnet protocol)


 Testing Results

# Test Command Executed

telnet localhost 23


# Test Result

Connecting to localhost...Could not open connection to the host, on port 23: Connect failed


# Conclusion
 SUCCESSFUL - The firewall rule is working correctly. Port 23 is blocked, and connections are refused.



 Key Concepts Learned

# 1. What is a Firewall?
A firewall is a network security system that monitors and controls inbound and outbound network traffic based on predetermined security rules. It acts as a barrier between a trusted internal network and untrusted external networks.

Functions:
- Filters network traffic
- Blocks unauthorized access
- Monitors connections
- Enforces security policies
- Prevents malware spread

# 2. Stateful vs Stateless Firewall

Stateful Firewall:
- Maintains connection state information
- Remembers previous connections
- More intelligent decision-making
- Modern and more secure
- Example: Windows Defender Firewall

Stateless Firewall:
- Examines each packet independently
- No memory of previous packets
- Simpler but less intelligent
- Faster processing
- Less secure

# 3. Inbound vs Outbound Rules

Inbound Rules:
- Control traffic ENTERING your computer
- Protect against external attacks
- Example: Block port 23 (our rule)

Outbound Rules:
- Control traffic LEAVING your computer
- Prevent malware communication
- Restrict data exfiltration

# 4. How UFW (Uncomplicated Firewall) Simplifies Management

UFW is a Linux firewall management tool that:
- Simplifies iptables configuration
- Uses intuitive command syntax
- Makes firewall configuration easier
- Example: `ufw allow 22/tcp` (simple instead of complex iptables commands)

# 5. Why Block Port 23 (Telnet)?

Telnet is insecure because:
- Transmits data in plain text (unencrypted)
- No secure authentication
- Vulnerable to eavesdropping - credentials can be captured
- Easy man-in-the-middle attacks
- SSH (port 22) is the secure alternative

Why we block it:
- Prevent unauthorized access
- Protect against credential theft
- Force use of secure alternatives
- Security best practice

# 6. Common Firewall Mistakes

1. Blocking all traffic (makes the system unusable)
2. Not updating rules (rules become outdated)
3. Overly permissive rules ("Allow all" defeats purpose)
4. Misconfiguring port forwarding (exposes services)
5. Not testing changes (rules may not work)
6. Ignoring logging (can't monitor what's blocked)
7. Using weak default configurations
8. Not backing up rules
9. Forgetting to document rules
10. Not monitoring logs

# 7. How Firewall Improves Network Security

Protection mechanisms:
- Access Control: Allows/blocks specific traffic types
- Threat Prevention: Blocks known malicious patterns
- Intrusion Prevention: Detects and blocks attacks
- Privacy Protection: Hides internal network structure
- Policy Enforcement: Ensures compliance
- Traffic Monitoring: Logs and alerts on suspicious activity
- DDoS Protection: Filters high-volume attacks

# 8. What is NAT (Network Address Translation)?

Definition:
NAT translates private IP addresses to public IP addresses and vice versa.

How it works:
1. Internal device sends traffic with private IP (e.g., 192.168.1.66)
2. Firewall intercepts and translates to a public IP
3. External server sees public IP, not private IP
4. Response comes back with public IP
5. Firewall translates back to private IP
6. Internal device receives response

Benefits:
- Privacy: Hides internal IP addresses
- Security: External users can't directly target internal IPs
- IP Conservation: Multiple devices share one public IP
- Automatic Filtering: Unsolicited traffic is blocked



 Interview Questions & Answers

Q1: What is a firewall?
A: A firewall is a network security system that monitors and controls inbound and outbound network traffic based on predetermined security rules.

Q2: What is the difference between a stateful and a stateless firewall?
A: Stateful firewalls maintain connection state and make intelligent decisions; stateless firewalls examine each packet independently without context.

Q3: What are inbound and outbound rules?
A: Inbound rules control traffic entering your computer; outbound rules control traffic leaving your computer.

Q4: How does UFW simplify firewall management?
A: UFW provides a simpler interface for managing iptables on Linux with intuitive syntax like `ufw allow 22/tcp`.

Q5: Why block port 23 (Telnet)?
A: Telnet is insecure - it transmits data in plain text without encryption, making credentials vulnerable to capture.

Q6: What are common firewall mistakes?
A: Blocking all traffic, not updating rules, overly permissive rules, not testing changes, ignoring logging, and weak default configurations.

Q7: How does a firewall improve network security?
A: By filtering unauthorized traffic, blocking attacks, preventing intrusions, hiding network structure, and monitoring activity.

Q8: What is NAT in firewalls?
A: NAT (Network Address Translation) translates private IPs to public IPs, providing privacy by hiding the internal network structure and improving security.



 Firewall Rules Summary

| Rule Name | Type | Protocol | Port | Action | Status |
|--||-||--|--|
| Block Telnet Port 23 | Inbound | TCP | 23 | Block | Enabled  |



 Screenshots

All screenshots are in the `screenshots/` folder showing:
1. Allowed apps configuration
2. Advanced Security interface
3. Inbound Rules list
4. New Rule wizard - type selection
5. Protocol and Port configuration
6. Action selection (Block)
7. Profile selection (Domain, Private, Public)
8. Rule naming and description
9. Completed rule in the Inbound Rules list
10. Test result - Telnet connection failed



 Learning Outcomes

✓ Firewall configuration and management
✓ Understanding port-based filtering
✓ Rule creation and testing
✓ Network traffic control
✓ Security best practices
✓ Understanding why blocking insecure protocols is important


WINDOWS FIREWALL RULES CREATED 

===========================================
RULE 1: Block Telnet Port 23
===========================================
Rule Type:    Inbound Rule
Protocol:     TCP
Port:         23
Action:       Block the connection
Profiles:     Domain, Private, Public
Status:       Enabled 
Description:  Blocks inbound connections on port 23 (Telnet protocol)

Testing:
- Command: telnet localhost 23
- Result:  Could not open connection to the host, on port 23: Connect failed
- Status:  WORKING - Rule successfully blocks port 23

===========================================
SUMMARY
===========================================
✅ Firewall rule created successfully
✅ Rule is enabled and active
✅ Test confirms rule is working
✅ Port 23 (Telnet) is blocked
✅ Insecure protocol is prevented
