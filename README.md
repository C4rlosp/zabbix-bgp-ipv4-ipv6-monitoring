Zabbix BGP IPv4/IPv6 SNMP Template for Cisco Routers (CRIX)

Official Zabbix template developed and tested by CRIX (Costa Rica Internet Exchange) for monitoring BGP IPv4 and IPv6 sessions on Cisco routers using SNMPv2.

✨ Features

✅ Auto-discovery of BGP peers (IPv4 & IPv6)

✅ Monitors BGP session state, remote ASN, and accepted prefixes

✅ Triggers alerts if a session is not in Established state

✅ Uses value mapping for clear BGP state names

✅ Designed for Cisco IOS XR (tested on NCS-5501)

📁 Files included

zabbix-bgp-ipv4-ipv6-template-crix/
├── templates/
│   └── zbx_template_bgp_ipv4_ipv6_crix_autodiscovery.yaml
├── screenshots/
│   ├── latest-data-example.png
│   └── telegram-alert-example.png
└── docs/
    └── how-it-works.md

⚖ Requisitos

Zabbix 6.0 o 7.0

SNMPv2 habilitado en el router Cisco

Comunidad SNMP accesible desde el servidor Zabbix

MIB CISCO-BGP4-MIB activa

🔄 Instalación

Importa el archivo YAML en Zabbix: Configuration → Templates → Import

Asigna el template al host Cisco con SNMPv2 habilitado

Asegura que la comunidad SNMP y la ACL permiten el acceso

Espera la ejecución del discovery (cada 5 min por defecto)

🚀 Ejemplo de monitoreo

Estado de sesión BGP (cbgpPeer2State)

ASN remoto del peer (cbgpPeer2RemoteAs)

Prefijos aceptados (cbgpPeer2AcceptedPrefixes)

🌎 Comunidad y autor

Desarrollado por el equipo técnico del CRIX – https://crix.crContact: Carlos Pérez @C4rlosp

📝 Licencia

MIT. Puedes usar, modificar y compartir libremente este template.
