Live demo →
https://hashsushil.github.io/clickjacking.lab/exploit.html

Clickjacking Attack

“तपाईंले जहाँ क्लिक गर्दै हुनुहुन्छ भन्ने सोच्नुहुन्छ — तर वास्तविकतामा कतै अर्कै ठाउँमा क्लिक भइरहेको हुन सक्छ।”
(You think you are clicking where you intend — but in reality, you may be clicking somewhere else entirely.)

A self-contained, interactive clickjacking demonstration lab built as part of my offensive security learning journey through PortSwigger Web Security Academy.

How This Lab Works

This lab contains two pages — both are self-made and self-hosted. No real third-party sites are targeted.

victim.html → Simulated FakeBank account settings page with a "Delete Account"
exploit.html → Attacker page with a decoy button layered over the hidden victim iframe
Attack Flow

Attacker crafts a URL with pre-filled parameters
                  ↓
Victim visits the link — sees a decoy "Claim your prize" page
                  ↓
Hidden iframe loads victim.html with attacker-controlled data
                  ↓
Victim clicks the decoy button
                  ↓
Actually clicks "Delete Account" on the victim page underneath

**URL Parameter Injection**

The attacker can pre-fill the victim's form fields by crafting a malicious URL:

victim.html?name=Falano+Sharma&email=falano@bank.com

This means the victim page auto-populates with attacker-controlled data before the user even clicks anything — making the attack more targeted and dangerous.
