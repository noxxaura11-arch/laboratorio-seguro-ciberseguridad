# Mi primer laboratorio seguro de ciberseguridad

## Objetivo

Implementar un entorno de laboratorio virtualizado con Windows 11 y Ubuntu para practicar configuración segura, actualizaciones, aislamiento de red y validación de conectividad.

## Entorno y configuración

- **Virtualizador:** Oracle VirtualBox.
- **Windows 11:** máquina `Pruebafacu`, dirección `192.168.50.10/24`.
- **Ubuntu 24.04.5 LTS:** máquina `Ubuntu-LAB-Auto`, equipo `ubuntu-lab`, dirección `192.168.50.20/24`.
- **Red compartida:** red interna de VirtualBox denominada `LAB` (`192.168.50.0/24`).
- **Conexión inicial:** NAT para instalar y actualizar Ubuntu; posteriormente se cambió a red interna.
- **Firewall Ubuntu:** UFW activo; se deniegan conexiones entrantes de forma predeterminada y se permiten las salientes.

## Actividades realizadas

1. Instalación de las máquinas virtuales y comprobación de arranque.
2. Actualización de paquetes en Ubuntu con `apt update` y `apt full-upgrade`.
3. Comprobación del estado de paquetes con `dpkg --audit`.
4. Activación de UFW y comprobación con `ufw status verbose`.
5. Configuración de direcciones IPv4 estáticas y aislamiento en la red interna `LAB`.
6. Prueba de conectividad con ICMP en ambos sentidos: **4 de 4 respuestas y 0 % de pérdida** en cada dirección.
7. Creación de instantáneas de estado seguro en ambas máquinas virtuales.

## Evidencias

| Archivo | Contenido |
| --- | --- |
| [Informe_Laboratorio_Seguro.pdf](Informe_Laboratorio_Seguro.pdf) | Informe completo de la práctica |
| [01_conectividad_bidireccional.png](evidencias/01_conectividad_bidireccional.png) | Ping entre Ubuntu y Windows en ambos sentidos |
| [02_instantanea_ubuntu.png](evidencias/02_instantanea_ubuntu.png) | Instantánea final de Ubuntu en VirtualBox |
| [03_firewall_red.png](evidencias/03_firewall_red.png) | Estado de UFW e identificación de la conexión de red |
| [04_actualizacion_integridad.png](evidencias/04_actualizacion_integridad.png) | Versión del sistema y comprobación de paquetes |

## Resultado

Se obtuvo un entorno de pruebas aislado para prácticas básicas de ciberseguridad. Los equipos pudieron intercambiar paquetes ICMP dentro de la red interna, sin pérdida en las pruebas finales. Las instantáneas permiten restaurar un estado inicial conocido.

> **Nota:** Este repositorio documenta el procedimiento. No contiene imágenes completas de discos virtuales ni credenciales de acceso.
