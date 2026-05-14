\# Docker-Bereitstellungsdokumentation



\## Übersicht



Die Infrastruktur-Dienste werden als Docker-Container auf einer Ubuntu-Server-virtuellen Maschine innerhalb der Proxmox-VE-Umgebung betrieben.



\## Bereitgestellte Dienste



\- Heimdall Dashboard

\- Nextcloud

\- Netdata Monitoring

\- Portainer Container-Verwaltung



\## Bereitstellungsarchitektur



Docker wird zur Isolation und Verwaltung der Infrastruktur-Dienste in separaten Containern eingesetzt. Interne Dienste werden über einen nginx Reverse Proxy geroutet und sicher über Cloudflare Tunnel extern bereitgestellt.



Administrative Dienste sind zusätzlich durch Cloudflare Zero Trust Access geschützt.



\## Betriebsumgebung



\- Host-Plattform Proxmox VE

\- Virtuelle Maschine Ubuntu Server

\- Container-Laufzeitumgebung Docker

\- Reverse Proxy nginx

\- Externer Zugriff Cloudflare Tunnel

\- Zugriffsschutz Cloudflare Zero Trust



\## Container-Startverhalten



Die Container sind so konfiguriert, dass sie nach einem vollständigen Neustart des Host-Systems automatisch wieder gestartet werden, um die Verfügbarkeit der Infrastruktur sicherzustellen.



Verwendete Restart-Richtlinie



docker update --restart unless-stopped



\## Monitoring \& Verwaltung



Die Überwachung und Verwaltung der Infrastruktur erfolgt über



\- Netdata für Echtzeit-Monitoring

\- Portainer zur Verwaltung der Docker-Container

\- Heimdall als zentrales Dashboard für den Infrastrukturzugriff



\## Troubleshooting-Erfahrungen



Während der Implementierung wurden verschiedene betriebliche Herausforderungen analysiert und erfolgreich gelöst, darunter



\- Persistenz des Docker-Container-Neustarts

\- DNS-Resolver-Konflikte

\- Startprobleme des Cloudflare Tunnels

\- Validierung der Reverse-Proxy-Routing-Konfiguration

\- Fehleranalyse bei externer Dienst-Erreichbarkeit

\- Wiederherstellung der Infrastruktur nach Systemneustart



\## Ergebnis



Die Docker-basierte Bereitstellung ermöglicht eine modulare, wartbare und skalierbare Service-Architektur innerhalb der selbst gehosteten Infrastruktur.

