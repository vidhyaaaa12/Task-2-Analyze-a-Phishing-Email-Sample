# Task-2-Analyze-a-Phishing-Email-Sample
This repository contains the analysis of a real phishing email sample as part of a cybersecurity internship task.
 Objective: Identify phishing characteristics in a suspicious email sample.
 Tools:  Email client or saved email file (text), free online header analyzer.
 Deliverables: A report listing phishing indicators found.

 ## Sample Overview

- Phishing Target: Bradesco / Livelo (Brazilian bank & loyalty program)
- Subject: “Seu cartão tem 92.990 pontos LIVELO expirando hoje!”
- Language: Portuguese
- Spoofed Sender: `banco.bradesco@atendimento.com.br`
- Malicious Link: `https://blog1seguimentmydomaine2bra.me/` (redirects to phishing domain)

##  Step 1: Obtain a Sample Phishing Email

- The phishing email was obtained directly from a *Gmail inbox*.
- It targeted Brazilian users and pretended to be from *Bradesco Livelo*, stating the user had *92,990 points expiring today*.
- The email was opened in Gmail, and *“Show original”* was used to extract full email headers and content.

## Step 2: Examine the Sender's Email Address

- From Address: `banco.bradesco@atendimento.com.br`
- Although it looks like a legitimate service address, Bradesco official domains typically end in `@bradesco.com.br`.
- This is a *spoofed email address* meant to impersonate the bank.
- Conclusion: Sender is fake.

#  Step 3: Check Email Headers for Discrepancies

- Gmail’s Show original revealed:
  - SPF: TempError
  - DKIM: Not Signed
  - DMARC: TempError
- Authentication failed or timed out — a sign of a *malformed or suspicious sender setup*.
- *Conclusion*: Header analysis confirms that the email failed proper validation.

##  Step 4: Identify Suspicious Links or Attachments

- The email contained a CTA button with the phrase: *“Resgatar Agora”* (Redeem Now)
- The *actual link* (decoded) was:https://blog1seguimentmydomaine2bra.me/

  - This link was submitted to [VirusTotal](https://www.virustotal.com/)
-  Result: Flagged as phishing by multiple security engines
-  Conclusion: URL is clearly phishing/malicious

---

##  Tools Used
##  Summary of Tools Used

| Step | Tool Used                              | Description                                                                 |
|------|----------------------------------------|-----------------------------------------------------------------------------|
| 1    | Gmail (Inbox)                          | Email obtained from real Gmail inbox                                        |
| 1    | Gmail “Show Original” (raw `.eml`)     | Used to access full email content and headers in `.eml` format              |
| 2    | Visual inspection                      | Checked for spoofed sender address manually                                 |
| 3    | Email header section (in `.eml`)       | Verified SPF, DKIM, and DMARC fields in header                              |
| 4    | [VirusTotal](https://www.virustotal.com/) | Used to analyze suspicious URL and check if flagged by security engines  |

### 5. Urgent or Threatening Language

The phishing email uses urgency and emotional pressure to manipulate the user:

- Subject line: “Seu cartão tem 92.990 pontos LIVELO expirando hoje!”
- Body message: “Resgate agora mesmo antes que eles expirem!” (Redeem now before they expire!)
- Emphasizes loss: Threatens the user that loyalty points will expire “HOJE” (Today) unless immediate action is taken.

This is a *classic urgency tactic* used in phishing to reduce critical thinking and prompt fast action.

### 6. Mismatched URLs

The link text shown in the email (e.g., "Clique aqui", "Resgatar Agora") *pretends to be a Bradesco or Livelo website*, but the actual URL redirects to:

https://blog1seguimentmydomaine2bra.me/

- This domain is clearly *not official*(doesn’t end in `bradesco.com.br` or `livelo.com.br`).
- It appears designed to *look vaguely Brazilian* or branded, but it is *fake and suspicious*.

This is a textbook case of a *mismatched URL* used to deceive the user.

---

### 7. Spelling or Grammar Errors

Although the email is in Portuguese and mostly grammatically correct, the tone and formatting show several issues:

- Robotic and repetitive phrasing like:
  - “Resgate agora mesmo antes que eles expirem!”
- Inconsistent use of capital letters (e.g., “HOJE”)
- Awkward phrasing not typical in real bank communication

These signs point to a poorly crafted *mass phishing attempt*, not an official corporate email.

---

### 8. Summary of Phishing Characteristics

| Category                  | Finding                                                                  |
|---------------------------|--------------------------------------------------------------------------|
| Spoofed Sender            | `banco.bradesco@atendimento.com.br` (fake domain)                        |
| Urgent Language           | Threat of point expiration "today", pushing the user to act immediately  |
| Suspicious Link           | Redirects to a fake domain (`.me`) pretending to be Bradesco             |
| Grammar/Tone              | Repetitive and unnatural Portuguese phrasing                             |
| Brand Abuse               | Uses fake Bradesco and Livelo branding/logos                             |

###  Conclusion:

This phishing email impersonates *Bradesco/Livelo* and tries to trick the recipient into clicking a malicious link. It uses scare tactics, suspicious URLs, and branding abuse to appear trustworthy, and is designed to *steal user credentials* or conduct fraud.






 
