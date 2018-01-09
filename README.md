# Proyecto2Redes
Este es el proyecto número 2 para la clase de Redes.

Realizado por:

Nathalia Ceballos Hurtado

Daniel Felipe Bueno

# Configuración para los dispositivos

-----------------------------------------------R1 server dhcp------------------------------------------------

R1#conf ter

R1(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.15

R1(config)# ip dhcp pool my-dhcp-server

R1(dhcp-config)# network 192.168.1.0 255.255.255.0

R1(dhcp-config)# default-router 192.168.1.1

R1(dhcp-config)# dns-server 192.168.1.7

R1(dhcp-config)# domain-name myexample.com


-----------------------------------------------R2 cliente dhcp-----------------------------------------------


R2#conf ter

R2(config)# interface f0/1

R1(config-if)# ip address dhcp

R1(config-if)# no shutdown

R1(dhcp-config)# end

R1# show ip interface f0/1



-----------------------------------------------Ubuntu-1-----------------------------------------------

cd /etc/network/

nano interfaces

-#

-# This is a sample network config uncomment lines to configure the network

-#


-# Static config for eth0

-#auto eth0

-#iface eth0 inet static

-#       address 192.168.0.2

-#       netmask 255.255.255.0

-#       gateway 192.168.0.1

-#       up echo nameserver 192.168.0.1 > /etc/resolv.conf

-# DHCP config for eth0

auto eth0

iface eth0 inet dhcp

