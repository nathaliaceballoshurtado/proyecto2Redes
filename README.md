# Proyecto2Redes
Este es el proyecto número 2 para la clase de Redes.

# Configuración para los dispositivos

-R1 server dhcp-

R1#conf ter

R1(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.15

R1(config)# ip dhcp pool my-dhcp-server

R1(dhcp-config)# network 192.168.1.0 255.255.255.0

R1(dhcp-config)# default-router 192.168.1.1

R1(dhcp-config)# dns-server 192.168.1.7

R1(dhcp-config)# domain-name myexample.com
