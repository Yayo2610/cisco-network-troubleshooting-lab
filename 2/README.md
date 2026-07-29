# Ejercicio 1.1 — Construir una Red SOHO Básica

**Curso:** Introducción a Redes (Cisco NetAcad) · **Herramienta:** Cisco Packet Tracer
**Tema:** Tipos de Redes y Componentes — Dispositivos finales e intermedios

## Objetivo

Construir una red doméstica/pequeña oficina (**SOHO – Small Office/Home Office**) para identificar los dispositivos finales y los dispositivos intermedios que la componen, y comprobar la conectividad entre ellos mediante el comando `ping`.

## Materiales y equipos utilizados

| Cantidad | Dispositivo | Modelo en Packet Tracer | Rol en la red |
|---|---|---|---|
| 3 | PC | PC-PT | Dispositivo final |
| 1 | Impresora | Printer-PT | Dispositivo final |
| 1 | Switch | Switch 2960 | Dispositivo intermedio |
| 4 | Cable de cobre | Copper Straight-Through | Medio de red |

## Topología

![Topología de la red SOHO](images/topologia.png)

## Tabla de direccionamiento IP

| Dispositivo | Interfaz | Dirección IP | Máscara de subred |
|---|---|---|---|
| PC0 | FastEthernet0 | 192.168.1.10 | 255.255.255.0 |
| PC1 | FastEthernet0 | 192.168.1.11 | 255.255.255.0 |
| PC2 | FastEthernet0 | 192.168.1.12 | 255.255.255.0 |
| Impresora | FastEthernet0 | 192.168.1.20 | 255.255.255.0 |

## Procedimiento realizado

1. **Colocar los dispositivos.** Se agregaron al lienzo de Packet Tracer 3 equipos PC-PT, 1 impresora (Printer-PT) y 1 switch (Switch 2960).
2. **Cablear la red.** Se conectó cada dispositivo final al switch utilizando cable de cobre recto (*Copper Straight-Through*).
3. **Configurar direcciones IP en las PC.** En cada PC, pestaña **Desktop > IP Configuration**, se asignó IP estática y máscara según la tabla de direccionamiento.
4. **Configurar la impresora.** En la impresora, pestaña **Config > FastEthernet**, se asignó la IP 192.168.1.20/24.
5. **Verificar el estado de los enlaces.** Los indicadores de enlace entre cada dispositivo y el switch quedaron en verde (enlace activo).
6. **Probar la conectividad.** Desde el símbolo del sistema (**Desktop > Command Prompt**) se ejecutó `ping` hacia el resto de los hosts de la red.

## Verificación y resultados

**Ping hacia 192.168.1.11**

![Resultado ping 192.168.1.11](images/ping-192-168-1-11.png)

**Ping hacia 192.168.1.12**

![Resultado ping 192.168.1.12](images/ping-192-168-1-12.png)

**Ping hacia 192.168.1.20 (impresora)**

![Resultado ping 192.168.1.20](images/ping-192-168-1-20.png)

| Destino | Paquetes enviados | Recibidos | Perdidos |
|---|---|---|---|
| 192.168.1.11 | 4 | 4 | 0 (0%) |
| 192.168.1.12 | 4 | 4 | 0 (0%) |
| 192.168.1.20 | 4 | 4 | 0 (0%) |

## Análisis

- **Dispositivos finales identificados:** PC0, PC1, PC2 e Impresora — origen o destino de los mensajes transmitidos en la red.
- **Dispositivo intermedio identificado:** Switch 2960 — dirige el tráfico entre los dispositivos finales sin ser el origen ni el destino de la comunicación.
- **Medio de red utilizado:** cable de cobre de par trenzado (Ethernet).

## Conclusión

En esta práctica se logró construir y verificar una red SOHO básica utilizando un switch como dispositivo intermedio para conectar tres PC y una impresora como dispositivos finales. La configuración de direcciones IP estáticas dentro de la misma red (192.168.1.0/24) permitió la comunicación directa entre todos los equipos sin necesidad de un router, confirmando que en una red pequeña de un solo segmento el switch es suficiente para que los dispositivos finales se "vean" entre sí. Las pruebas de `ping` resultaron exitosas entre todos los hosts, validando tanto el cableado como el direccionamiento realizado.
