# Despliegue de Túnel VPN WireGuard & Persistencia de Sesión en Alta Disponibilidad (OCI + Linux)

## 1. Problema de Negocio / Arquitectura
- Mitigación de desconexiones VoIP y sesiones críticas ante conmutación de enlaces ISP físicos.
- Requerimiento de IP pública persistente y enrutamiento seguro de baja latencia.

## 2. Topología y Diseño de Red
- **Cube / VPS:** Oracle Cloud Infrastructure (Ubuntu Server 24.04).
- **Subredes:** VCN 10.0.0.0/16, interfaz local `ens3` (10.0.0.71), túnel `wg0` (10.8.0.0/24).
- **Políticas de Seguridad:** Reglas de entrada Stateful (UDP 51820) e inspección en Security Lists.

## 3. Implementación Técnica
- Habilitación de reenvío de paquetes en kernel Linux (`net.ipv4.ip_forward = 1`).
- Generación de claves criptográficas asimétricas (Curve25519) con permisos restringidos (`umask 077`).
- Enrutamiento dinámico y SNAT mediante `iptables` (`MASQUERADE`).
- Configuración de Keepalive para atravesar NATs restrictivos (Carrier-Grade NAT).

## 4. Pruebas de Conectividad y Validación
- Diagnóstico con `wg show`, tablas de rutas del kernel y verificación de tráfico bidireccional.