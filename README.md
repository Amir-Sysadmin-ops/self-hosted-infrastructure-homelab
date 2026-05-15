\# Self-Hosted Infrastrukturprojekt



\## Einführung



Dieses Repository dokumentiert den eigenständigen Aufbau, die Konfiguration und den Betrieb einer modernen selbst gehosteten Infrastruktur auf Basis von Virtualisierung, Containerisierung, Reverse Proxy Routing, Monitoring sowie sicherer externer Bereitstellung.



Ziel des Projekts war die praktische Umsetzung einer modularen Infrastrukturumgebung zur Bereitstellung und Verwaltung verschiedener Dienste unter Berücksichtigung moderner Sicherheits- und Betriebsanforderungen.



Die Infrastruktur wurde vollständig eigenständig geplant, implementiert, abgesichert, getestet und dokumentiert.



\---



\## Systemarchitektur



Die Infrastruktur basiert auf einer mehrschichtigen Architektur zur Trennung von Virtualisierung, Containerisierung, Netzwerkzugriff, Monitoring und Sicherheitskontrolle.



\### Verwendete Komponenten



\- Proxmox VE als Virtualisierungsplattform

\- Ubuntu Server als zentrale Verwaltungs- und Betriebsumgebung

\- Docker zur Containerisierung einzelner Dienste

\- nginx als Reverse Proxy für internes Routing

\- Cloudflare Tunnel zur sicheren externen Bereitstellung

\- Cloudflare Zero Trust Access zur Zugriffskontrolle administrativer Dienste

\- Heimdall als zentrales Dashboard

\- Nextcloud als private Cloud-Lösung

\- Netdata zur Infrastrukturüberwachung

\- Portainer zur Docker-Container-Verwaltung



\---



\## Architekturdiagramm



!\[Architekturdiagramm](./screenshots/architecture-diagram.png)



\---



\## Deployment-Architektur



Die Dienste werden innerhalb einer Ubuntu-Server-VM betrieben, welche auf Proxmox VE gehostet wird.



Die Containerisierung erfolgt über Docker, wodurch die einzelnen Dienste logisch voneinander getrennt und unabhängig verwaltbar bleiben.



Externe Anfragen werden über Cloudflare Tunnel entgegengenommen und sicher an den internen nginx Reverse Proxy weitergeleitet.



Der Reverse Proxy übernimmt die interne Routing-Logik zu den jeweiligen Diensten.



Administrative Dienste werden zusätzlich durch Cloudflare Zero Trust abgesichert.



\---



\## Bereitgestellte Dienste



\### Nextcloud



Nextcloud dient als private selbst gehostete Cloud-Lösung zur Datei- und Datenverwaltung.



!\[Nextcloud](./screenshots/nextcloud.png)



\---



\### Heimdall Dashboard



Heimdall dient als zentrale Verwaltungsoberfläche für die Infrastruktur und den Zugriff auf interne Dienste.



!\[Heimdall Dashboard](./screenshots/heimdall.png)



\---



\### Netdata Monitoring



Netdata ermöglicht die Echtzeitüberwachung von CPU, Arbeitsspeicher, Netzwerkverkehr und Systemressourcen.



!\[Netdata Monitoring](./screenshots/netdata.png)



\---



\### Portainer



Portainer dient der Verwaltung und Überwachung der Docker-basierten Infrastruktur.



!\[Portainer](./screenshots/portainer.png)



\---



\## Virtualisierung \& Containerbetrieb



\### Proxmox VE



Proxmox VE stellt die zugrunde liegende Virtualisierungsplattform für den Betrieb der Infrastruktur bereit.



!\[Proxmox Dashboard](./screenshots/proxmox.png)



\---



\### Docker



Docker wird zur Isolation und Verwaltung der einzelnen Infrastruktur-Dienste eingesetzt.



!\[Docker Container Übersicht](./screenshots/docker.png)



\---



\## Sicherheitsarchitektur



Sicherheit war ein zentrales Designziel dieses Projekts.



Implementierte Sicherheitsmaßnahmen:



\- Cloudflare Tunnel zur sicheren externen Bereitstellung

\- Verzicht auf klassische direkte Portweiterleitungen

\- Zugriffsschutz durch Cloudflare Zero Trust

\- HTTPS-basierter externer Zugriff

\- Reverse Proxy Routing über nginx

\- Container-Isolation durch Docker

\- Trennung interner Dienste



\### Cloudflare Tunnel



!\[Cloudflare Tunnel](./screenshots/cloudflare-tunnel.png)



\---



\### Cloudflare Zero Trust



!\[Cloudflare Zero Trust](./screenshots/cloudflare-zero-trust.png)



\---



\## Reverse Proxy Konfiguration



Die interne Routing-Logik wird über nginx Reverse Proxy umgesetzt.



Die Konfigurationsdatei befindet sich unter:



configs/nginx.conf



\---



\## Docker Deployment Dokumentation



Die Docker-bezogene Betriebsdokumentation befindet sich unter:



configs/docker-notes.md



\---



\## Troubleshooting \& Betriebliche Herausforderungen



Während der Implementierung wurden verschiedene reale Infrastrukturprobleme analysiert und erfolgreich gelöst.



\### Gelöste Probleme



\- Docker-Container starteten nach Neustart nicht automatisch

\- DNS-Resolver-Konflikte durch Tailscale-Konfiguration

\- Cloudflare Tunnel Startprobleme

\- Reverse Proxy Routing Fehler

\- Fehleranalyse bei externer Dienst-Erreichbarkeit

\- Wiederherstellung der Infrastruktur nach vollständigem Host-Neustart

\- Netzwerk- und Routing-Debugging



Diese Herausforderungen führten zu praxisnaher Erfahrung im Bereich Infrastruktur-Betrieb und Systemadministration.



\---



\## Repository-Struktur



self-hosted-infrastructure-homelab/

├── README.md

├── .gitignore

├── documentation/

├── screenshots/

└── configs/



\---



\## Dokumentation



Zusätzliche Projektdokumentation:



\- Infrastruktur-PDF-Dokumentation

\- Architekturdiagramm

\- Konfigurationsdateien

\- Docker Deployment Notizen



\---



\## Zukünftige Erweiterungen



Geplante Weiterentwicklungen:



\- Docker Compose basierte Deployment-Automatisierung

\- Backup-Strategie

\- Monitoring-Erweiterungen

\- VPN-basierter interner Zugriff

\- Automatisierte Infrastrukturverwaltung

\- Infrastructure as Code

\- CI/CD Integration



\---



\## Fazit



Dieses Projekt demonstriert den eigenständigen Aufbau, Betrieb, die Absicherung und Dokumentation einer modernen selbst gehosteten Infrastruktur.



Durch die praktische Umsetzung wurden fundierte Kenntnisse in den Bereichen:



\- Linux-Systemadministration

\- Docker-Containerisierung

\- Reverse Proxy Routing

\- Netzwerkmanagement

\- DNS-Konfiguration

\- Monitoring

\- Sicherheitsarchitektur

\- Infrastruktur-Betrieb

\- Troubleshooting



praktisch aufgebaut und angewendet.

