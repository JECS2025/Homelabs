# Configuring Our Workstation (WS01)

Owner: JECS2025

---

## 🗂️ Contents
1. [Join the Domain & Configure DNS](#1-join-the-domain--configure-dns)
2. [Verify Domain User Login](#2-verify-domain-user-login)
3. [Test Network Access](#3-test-network-access)

---

## 1. Join the Domain & Configure DNS

- Set IP to **DHCP (via DC01)**.
- Go to: Settings > System > About

![Join Domain Prompt](./assets/ws01/Join_Domain.png)

- Select **Domain** → Enter `newcorp.local`.
- Provide **Domain Admin credentials**.
- Restart WS01.

---

## 2. Verify Domain User Login

- Login as a domain user (e.g., `testuser@newcorp.local`)

![Login Verification](./assets/ws01/Verify_Login.png)

![Login Confirmation](./assets/ws01/Verify_Login1.png)

*I’ll be using ‘Tester Test’ as the account that’ll verify all my future security implementations work.*

---

## 3. Test Network Access

- Ping **DC01** → `ping 172.16.0.1`
- Ping **FS01** → `ping 172.16.0.20`
- Test file access → `\\NewCorp-FS01\Shared` in File Explorer
