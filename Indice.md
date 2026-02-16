Proyecto Final de Ciberseguridad 4Geeks Academy Informe Forense y Pentesting — Caso de Incidente en Servidor Debian en 4Geeks Alumno: Victor Bravo Moreno
Fase 1 Autopsia\
1.- Autopsia	\
1.1 Logs Apache2	\	
1.2 Descubrimientos de los Log	\
1.3 Localizando usuarios y hashes	\
1.4 Conclusión	\
FASE 2 RedTeam Pentesting and Exploit	\
2.- Reconocimiento	\
2.1 Reconocimiento del objetivo y la red.	\
2.2 Versiones y Vulnerabilidades	\
Servicio FTP — vsftpd 3.0.3	\
Servicio SSH — OpenSSH 9.2p1	\
Servicio HTTP — Apache httpd 2.4.62	\
2.3 Análisis WordPress puerto 80.	\
Servicio HTTP — WordPress Core 6.9.1	\
2.4 Conexión FTP usando anonymous	\
2.5 SSH remoto	\
2.6 Investigacion y recopilacion	\
2.7 Acceso bases de datos, exploración y robo de información	\
2.8 Explotación vulnerabilidad y ataque a máquina	\
2.8.1 Creación Script	\
2.8.2 Monitorización y ejecución	\
2.9 Conclusiones Pentesting y Explotación.	\
FASE 3 BlueTeam and Hardening	\
3.1 PLAN DE RECUPERACIÓN DE LA MÁQUINA DEBIAN	\
3.2 Bloqueo de servicios y sanitización.\	
3.2.1 FTP puerto 21	\
3.2.2 SSH BLOQUEO DE SERVICIO	\
3.3 Limpieza usuarios no seguros MariaDB.	\
3.4 Limpieza man-db, apt compat y apt.systemd.daily	\
3.5 Instalación y configuración de antivirus.\	
3.6 Sanitizacion Wordpress	\
3.7 Configuración Apache2 por puerto 443	\
3.8 Instalación Agente Wazuh.	\
3.9 Instalación RKHUNTER y utilización	\
3.10 Usuario debian.	\
FASE 4 Plan de respuesta de incidentes y certificación	\
4.1  Plan de respuesta a incidentes y SGSI (Seguridad Gestionada – ISO 27001)	\
4.1.1: Creación del Plan de Respuesta a Incidentes (NIST SP 800-61)	\
4.1.3: Implementación de mecanismos de protección de datos (backups, cifrado, control de accesos)	\
4.1.4: Plan de respuesta a incidentes y SGSI	\
4.1.5 Recomendaciones de Data Loss Prevention (DLP)	\
4.1.6 Formalización del plan de recuperación y continuidad del negocio	\
4.1.7 Presentación ejecutiva de resultados	\
4.2 Conclusión y Referencias	\
5.CONCLUSIONES	\
6.RESUMEN EJECUTIVO	\
6.1 Objetivo	85 \
6.2 Alcance del análisis	85 \
6.4 Impacto potencial	86 \
6.5 Medidas correctivas aplicadas	86 \
6.6 Conclusión ejecutiva	87 \
7. INFORME TÉCNICO	87 \
7.1 Objetivo del informe técnico	87 \
7.2 FASE 1 – ANÁLISIS FORENSE	87 \
7.2.1 Herramienta utilizada	87 \
7.2.2 Análisis de logs Apache2	87 \
7.2.3 Análisis con journalctl	88 \
7.2.4 Usuarios y credenciales inseguras	88 \
7.2.5 Persistencia y archivos sospechosos	88 \
7.2.6 Conclusión forense	89 \
7.3 FASE 2 – RECONOCIMIENTO Y PENTESTING	89 \
7.3.1 Descubrimiento de puertos y servicios	89 \
7.3.2 Enumeración de versiones	89 \
7.3.3 Enumeración WordPress y fuzzing web	89 \
7.3.4 Acceso FTP anonymous	89 \
7.3.5 Acceso SSH con credenciales por defecto	90 \
7.3.6 Acceso y exfiltración de bases de datos	90 \
7.3.7 Ataque de Denegación de Servicio	90 \
7.3.8 Conclusión de la fase ofensiva	90 \
7.4 FASE 3 – RECUPERACIÓN Y HARDENING	91 \
7.4.1 Restauración desde snapshot	91 \
7.4.2 Actualización del sistema	91 \
7.4.3 Hardening FTP	91 \
7.4.4 Hardening SSH	91 \
7.4.5 Limpieza MariaDB	91 \
7.4.6 Reparación de archivos críticos del sistema	91 \
7.4.7 Instalación de antivirus y herramientas defensivas	91 \
7.4.8 Detección de rootkits con rkhunter	92 \
7.4.9 Recuperación WordPress y HTTPS	92 \
7.4.10 Fortalecimiento del usuario debian	92 \
7.5 FASE 4 – PLAN DE RESPUESTA A INCIDENTES Y SGSI	92 \
7.5.1 Plan de respuesta basado en NIST SP 800-61	92 \
7.5.2 SGSI basado en ISO 27001	92 \
7.5.3 Recomendaciones DLP, backups y cifrado	93 \
7.6 Conclusión técnica final	93 \
8.1 HERRAMIENTAS UTILIZADAS	93 \
Autopsy	93 \
journalctl	93 \
Nmap	93 \
Gobuster	94 \
FTP (vsftpd)	94 \
OpenSSH (SSH)	94 \
MariaDB / MySQL	94 \
mysqldump	94 \
SCP	94 \
htop	94 \
df -h / watch	94 \
cron / crontab	94 \
apt / apt-get	95 \
debsums	95 \
UFW (Uncomplicated Firewall)	95 \
ClamAV	95 \
Wazuh Agent	95 \
rkhunter	95 \
WordPress	95 \
Apache2	95 \
8.2 Fuentes oficiales	96 \
Debian Documentation	96 \
Apache HTTP Server Documentation	96 \
WordPress Developer Documentation	96 \
OpenSSH Manual / man pages	96 \
vsftpd Documentation	96 \
MariaDB Documentation	96 \
ClamAV Documentation	96 \
Wazuh Documentation	96 \
rkhunter Documentation 96  \
Bases de datos de vulnerabilidades y CVEs	97\
NIST NVD (National Vulnerability Database)	97\
MITRE CVE	97\
Exploit-DB	97\
INCIBE (Instituto Nacional de Ciberseguridad)	97\
Fuentes de ciberseguridad y hardening	97\
OWASP	97\
SANS Institute	97\
Red Hat Security Guides	97\
CIS Benchmarks	97\
Estándares y marcos utilizados	98\
NIST SP 800-61 (Computer Security Incident Handling Guide)	98\
ISO/IEC 27001 e ISO/IEC 27002	98\
ISO 27005	98\
Herramientas ofensivas y documentación práctica	98\
Kali Linux Documentation	98\
man pages Linux	98\
Blogs técnicos y artículos especializados	98\
