# Oracle Cloud Infrastructure (OCI) – VCN, Security Lists, and CIDR Blocks

## 🔹 Virtual Cloud Network (VCN)
- A **VCN (Virtual Cloud Network)** in OCI is like your own private data center in the cloud.
- In this example, we’re creating a **VCN with a /16 CIDR block**.
- Subnets inside the VCN will use smaller ranges (e.g., `/24`).

<img src="https://github.com/user-attachments/assets/26d55437-a430-4670-b88c-606948052c93" width="700" />

---

## 🔹 Security Lists: Ingress & Egress
- **Ingress rules**: Control incoming traffic (who can reach your resources).  
- **Egress rules**: Control outgoing traffic (where your resources can connect to).  
- These are used to **allow or disable specific port traffic** (like SSH, HTTPS, etc.).

<img src="https://github.com/user-attachments/assets/571822a3-4767-49b2-b3c6-b8516b879e64" width="700" />

**Example Rules:**
- Ingress: Allow TCP 22 (SSH) from your IP.
- Ingress: Allow TCP 443 (HTTPS) from the internet.
- Egress: Allow all TCP 443 (outbound HTTPS) for system updates.

<img src="https://github.com/user-attachments/assets/aaf75b87-6951-47aa-ad2e-350ac2bbd4df" width="700" />

---

## 🔹 CIDR Blocks and Overlaps
- CIDR blocks define the **IP address range** of your VCN.
- **Important:** You don’t want overlapping CIDRs between VCNs or subnets.
- Overlaps cause **routing conflicts** and break **VCN peering / connectivity**.

<img src="https://github.com/user-attachments/assets/91dfac49-1382-45ed-aa31-5b95d4fff771" width="700" />

**Bad Example (Overlap):**
- VCN A: `10.0.0.0/16`
- VCN B: `10.0.0.0/16` ❌

**Good Example (No Overlap):**
- VCN A: `10.0.0.0/16`
- VCN B: `10.1.0.0/16` ✅

<img src="https://github.com/user-attachments/assets/b0ccb4d4-77d0-4db7-9a2f-d4c2bda20355" width="700" />

---

## 🔹 Putting It All Together
Below are examples of how a VCN is structured with CIDR blocks, subnets, and security lists:

<img src="https://github.com/user-attachments/assets/2d4ca558-5426-4c47-9ace-f5ee5840e761" width="700" />
<img src="https://github.com/user-attachments/assets/13087778-1207-40f1-8b4b-ab6fed800088" width="700" />
<img src="https://github.com/user-attachments/assets/c90c7656-d8ee-41b2-9ec3-6348b8e812cf" width="700" />
<img src="https://github.com/user-attachments/assets/3de0e3cf-dbf3-4875-b40a-ab7f2bfcb180" width="700" />

---

## ✅ Key Takeaways
- **VCN** defines your private network space using CIDR blocks.  
- **Security Lists** use Ingress/Egress rules to control **port traffic**.  
- **Avoid overlapping CIDRs** to prevent routing and peering conflicts.  
