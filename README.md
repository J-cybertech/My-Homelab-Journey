# 🏠 My Homelab Journey

After experimenting with port forwarding and remote desktop access, I realized how exposed my network was to the internet. I wanted a **more secure, flexible, and private way to run services at home**. Over time, I built a homelab stack using **Proxmox**, **CasaOS**, **Pi-hole**, and **Tailscale**, with **Twingate** as an alternative VPN solution for more enterprise-grade zero-trust security.

---

## 🔧 How Each Tool Helps

| Tool       | Role in My Homelab |
|------------|------------------|
| **Proxmox** | Runs multiple virtual machines and containers on a single server, letting me isolate services safely. |
| **CasaOS** | Provides a user-friendly dashboard to manage apps and storage without digging into the command line. |
| **Pi-hole** | Blocks ads and trackers network-wide while giving me insight and control over DNS traffic. |
| **Tailscale** | Creates a secure, zero-config VPN for remote access, replacing risky port forwarding. |
| **Twingate** | Alternative VPN option with a zero-trust model, granular access controls, and detailed audit logging. |

---

## 🚀 Why I Chose This Stack
- Consolidates workloads and isolates services safely with **Proxmox**.  
- Makes app deployment and storage management easy with **CasaOS**.  
- Protects my privacy and network with **Pi-hole**.  
- Enables secure remote access without opening my network to the world using **Tailscale** or **Twingate**, depending on my needs.  

This setup lets me experiment, learn, and run a fully functional home server environment while keeping security and privacy top of mind.




# CasaOS-Project

  Creating a HyperVm that's running Debian 12 no GUI, hosting CasaOS to manage several other projects. Used HyperVm for the purpose of learning another virtual host other then VirtualBox. With HyperVm I learned the difference between the three virtual switches: External, Internal, Private. CasaOS is a open-source community project that allows you to build a personal cloud system in a docker ecosystem; which is super user-friendly. Once installed you can browse "apps" that are included in the "App store". You are able to add more packages from the [Casa github repo](https://awesome.casaos.io/content/3rd-party-app-stores/list.html#_2-casaos-appstore-play). 

![Alt text](images/casaos.png)


#      Other projects 
  [![Pi-Hole](https://img.shields.io/badge/pihole-%2396060C.svg?style=for-the-badge&logo=pi-hole&logoColor=white/)](https://pi-hole.net/)
 [![Twingate](https://img.shields.io/badge/Twingate-FFFFFF?style=for-the-badge&logo=susetwingate&logoColor=000000)](https://www.twingate.com)
[![RustDesk](https://img.shields.io/badge/RustDesk-1296DB?style=for-the-badge&logo=rustdesk)](https://rustdesk.com)
[![Tailscale](https://img.shields.io/badge/Tailscale-000000?style=for-the-badge&logo=tailscale)](https://tailscale.com)

 As I started my journey in learning more about this field, I wanted an aternative way to remote into my network that's more secure then just leaving my network open. I found this [video](https://youtu.be/sax55mrOX54?si=Sw2JB6fEf78CMCiX) which lead me into this rabbit hole of information. I've started by setting up Windows Firewall rules, changed RDP port within registry editor. Made sure my account has a strong passwords to minimize risk and used network-level authentication when enabling remote access. After a few months in this project I've notice alot of security logs from overseas like Bulgaria, Belgium, England, Luxembourg to name a few places. Trying to login with users like admin/administrator. While my OPSEC was strong, I wanted to reduce the risk futher. I've learned how to block ip address but without a Firewall router it would still be a pain. So I've looked into hosting tailscale and twingate. 

## 🔐 Twingate vs Tailscale

| Feature / Factor        | **Tailscale** 🚀 | **Twingate** 🛡️ |
|-------------------------|------------------|-----------------|
| **Ease of Setup**       | Very easy, plug-and-play | More complex, requires configuration |
| **Security Model**      | Mesh VPN (WireGuard) with ACLs | Zero Trust, micro-segmentation, least privilege |
| **Performance**         | Fast, peer-to-peer (WireGuard) | Relay-based; can be slower if UDP is blocked |
| **Admin Tools**         | Basic logging, ACLs, CLI, SSH support | Detailed audit logs, dashboards, MFA, device posture |
| **Platform Support**    | Windows, macOS, Linux, iOS, Android, Synology, etc. | Wide OS support, strong enterprise identity integrations |
| **Pricing**             | Generous free tier; affordable paid plans | Free tier + paid plans for advanced features |
| **Best For**            | Individuals, small teams, developers | Enterprises, organizations needing strict access controls |

Deploy a recursive Pi-Hole DNS sinkhole on a Raspberry Pi to improve network security by blocking unwanted ads, tracking domains, and malicious websites. Configure Pi-Hole to filter DNS requests at the network level, preventing devices from accessing harmful or undesirable content. Regularly update blocklists and fine-tune settings to optimize performance, reduce security vulnerabilities, and ensure the protection of all connected devices from potential threats.
![Alt text](images/pihole-unbound.png)

##  Pi-hole + Unbound (pihole-unbound)

| Feature / Factor             | Description |
|------------------------------|-------------|
| **What It Is**               | A setup that combines Pi-hole with Unbound, a validating recursive DNS resolver, allowing Pi-hole to resolve queries without relying on external DNS providers. :contentReference[oaicite:0]{index=0} |
| **Privacy & Security**       | Since Unbound performs lookups directly from root servers, it prevents upstream DNS logging and mitigates threats like DNS cache poisoning—enhancing privacy. :contentReference[oaicite:1]{index=1} |
| **DNSSEC Validation**        | Unbound provides DNSSEC support, allowing Pi-hole to verify authenticity of DNS responses, filtering out fraudulent or altered responses. :contentReference[oaicite:2]{index=2} |
| **Performance & Caching**    | Initial queries may be slower, but once cached, subsequent lookups are efficient—typically under 0.1 seconds. :contentReference[oaicite:3]{index=3} |
| **Setup Simplicity**         | Straightforward to set up on Debian/Ubuntu: install with `apt`, add Unbound config, and point Pi-hole at `127.0.0.1#5335`. :contentReference[oaicite:4]{index=4} |
| **Docker Integration**       | Several containerized options exist:



 
 ---- (add another project here, how to enable RDP and have it open to the internet)

Rustdesk and Twingate was my first runner up. Twingate is a zero trust network access, offering an alternative to traditional VPNs. Rustdesk is an open-source remote desktop with self-hosted server, encrypting any connections.


    How To
            


    Credits
        To - Networkchuck
            - CasaOS team
            -rustdesk
