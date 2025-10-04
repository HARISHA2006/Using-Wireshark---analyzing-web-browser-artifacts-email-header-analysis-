# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/11e23b41-4664-4c93-b2b9-626c0cd3e9ad" />

<img width="1600" height="1009" alt="image" src="https://github.com/user-attachments/assets/ffbc2031-b1e8-4d15-b9a0-30ad18052a2d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/575fc0fc-494d-4b7b-8fc5-28c602819209" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f457158f-7956-4684-8ecd-8030dc175404" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4abe6c42-f052-4470-81d0-f5e897348562" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/974964b2-6d1a-4bbd-af85-2974399f5976" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fedf2721-4829-43aa-8fbb-057f2dd15a8c" />


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

