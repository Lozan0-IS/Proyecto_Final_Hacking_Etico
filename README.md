Proyecto Final de Hacking Ético — Alan Israel Lozano Tavarez
Ataque controlado, explotación, post-explotación y documentación técnica
📌 Descripción del Proyecto

Este repositorio contiene el Proyecto Final de Hacking Ético, realizado en un entorno totalmente controlado.
El objetivo fue llevar a cabo un ataque completo a una máquina Windows 7 vulnerable, aplicando las fases del pentesting:

Reconocimiento pasivo y activo

Escaneo de servicios y detección de vulnerabilidades

Explotación con Metasploit

Post-explotación y extracción de evidencias

Persistencia en el sistema

Análisis técnico y documentación de resultados

Todos los informes, capturas y reportes generados están organizados dentro de este repositorio.

🧪 1. Reconocimiento y Escaneo
🔎 Escaneo con Nmap

Se identificaron servicios abiertos y la vulnerabilidad crítica MS17-010 (EternalBlue) mediante:

nmap -p- -sV -O -T4
nmap --script smb-vuln-ms17-010


Esto confirmó que el sistema era vulnerable a ejecución remota a través de SMBv1.

🌐 2. Escaneo Web con Nikto

Se realizó un análisis del servidor web de la máquina víctima, detectando configuraciones inseguros, cabeceras faltantes y rutas expuestas.

El reporte completo se encuentra en:
📄 Informe Nikto

💥 3. Explotación – EternalBlue (MS17-010)

Utilizando Metasploit Framework, se ejecutó:

exploit/windows/smb/ms17_010_eternalblue


El exploit permitió:

Acceso remoto con privilegios

Sesión Meterpreter estable

Control total del sistema comprometido

🛰️ 4. Post-Explotación

Dentro de la sesión Meterpreter se realizaron acciones como:

Extracción de archivos desde el escritorio de la víctima

Keylogging (captura de texto escrito por el usuario)

Enumeración del sistema

Obtención de credenciales y hashes

Mapeo de red y procesos

🔐 5. Persistencia

Se configuró un mecanismo de persistencia que permite recuperar acceso incluso después de reiniciar la máquina víctima.
Esto incluyó:

Creación de usuario privilegiado

Ejecución automática de un payload

Comprobación desde Windows de que la persistencia es efectiva

📂 Contenido del Repositorio
/Proyecto_Final_Hacking_Etico
   ├── Informe_Nmap.pdf
   ├── Informe_Nikto.pdf
   ├── Proyecto_Final_Hacking_Etico.pdf
   ├── Evidencias/
   └── README.md

🎯 Conclusiones

El proyecto permitió ejecutar un ataque realista siguiendo un flujo profesional de pentesting.
Se demostró:

Capacidad para identificar y explotar vulnerabilidades reales

Dominio de herramientas como Nmap, Nikto y Metasploit

Comprensión de la importancia del reconocimiento previo

Uso de técnicas avanzadas de post-explotación

Implementación efectiva de persistencia

Documentación técnica clara del ciclo completo del ataque

👨‍💻 Autor

Alan Israel Lozano Tavarez
