> Human beings face ever more complex and urgent problems, and their effectiveness in dealing <mark style="background: #FF5582A6;">with these problems is</mark> a matter that is critical to the stability and continued progress of society. \- Doug Engelbart, 1961
> 



About router:
if you assign a ip address to a port of a router automatically are assigned two kind of routes to the router. 
To check for route on a router or a pc you use   

![[lab11.png]]
Iniziamo considerando come configurati i pc con gateway l'interfaccia del router
pc1 
C:\>ipconfig
FastEthernet0 Connection:(default port)
Connection-specific DNS Suffix..:
Link-local IPv6 Address.........: FE80::201:C7FF:FED7:5066
IPv6 Address....................: ::
IPv4 Address....................: 192.168.1.1
Subnet Mask.....................: 255.255.255.0
Default Gateway.................: ::192.168.1.254

pc2
C:\>ipconfig
FastEthernet0 Connection:(default port)
Connection-specific DNS Suffix..:
Link-local IPv6 Address.........: FE80::2E0:A3FF:FE2A:C962
IPv6 Address....................: ::
IPv4 Address....................: 192.168.3.1
Subnet Mask.....................: 255.255.255.0
Default Gateway.................: :: 192.168.3.254



><mark style="background: #FF5582A6;">Router>enable</mark>
><mark style="background: #FF5582A6;">Router#conf t</mark>
Enter configuration commands, one per line. End with CNTL/Z.

><mark style="background: #FF5582A6;">Router(config)#hostname R1</mark>
>R1(config)#

>R1(config)#int g0/1
>R1(config-if)#ip add 192.168.1.254 255.255.255.0

><mark style="background: #FF5582A6;">R1(config-if)#do sh ip int brief</mark>
Interface IP-Address OK? Method Status Protocol
GigabitEthernet0/0 unassigned YES unset administratively down down
GigabitEthernet0/1 192.168.1.254 YES manual administratively down down
GigabitEthernet0/2 unassigned YES unset administratively down down
Vlan1 unassigned YES unset administratively down down

><mark style="background: #FF5582A6;">R1(config-if)#no shut
R1(config-if)#</mark>
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up
R1(config-if)#do sh ip int brief
Interface IP-Address OK? Method Status Protocol
GigabitEthernet0/0 unassigned YES unset administratively down down
GigabitEthernet0/1 192.168.1.254 YES manual up up
GigabitEthernet0/2 unassigned YES unset administratively down down
Vlan1 unassigned YES unset administratively down down

><mark style="background: #FF5582A6;">R1#sh ip route</mark>
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
>* - candidate default, U - per-user static route, o - ODR
P - periodic downloaded static route
Gateway of last resort is not set
192.168.1.0/24 is variably subnetted, 2 subnets, 2 masks
<mark style="background: #CACFD9A6;">C 192.168.1.0/24 is directly connected, GigabitEthernet0/1
L 192.168.1.254/32 is directly connected, GigabitEthernet0/1</mark>

Osserva in questo caso come dare un IP a un interfaccia automaticamente crea due route una alla rete a cui IP address appartiene e una come loopback al solo indirizzo di rete a.b.c.d/32
proseguendo nei vari settaggi andiamo per ordine . 

><mark style="background: #FF5582A6;">R1#conf t</mark>
Enter configuration commands, one per line. End with CNTL/Z.
<mark style="background: #FF5582A6;">R1(config)#int g0/0</mark>
<mark style="background: #FF5582A6;">R1(config-if)#ip address 192.168.12.1 255.255.255.0</mark>
<mark style="background: #FF5582A6;">R1(config-if)#no shut</mark>
<mark style="background: #FF5582A6;">R1#sh ip route</mark>
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
Gateway of last resort is not set
<mark style="background: #FFF3A3A6;">192.168.1.0/24 is variably subnetted, 2 subnets, 2 masks
C 192.168.1.0/24 is directly connected, GigabitEthernet0/1
L 192.168.1.254/32 is directly connected, GigabitEthernet0/1
192.168.12.0/24 is variably subnetted, 2 subnets, 2 masks
C 192.168.12.0/24 is directly connected, GigabitEthernet0/0
L 192.168.12.1/32 is directly connected, GigabitEthernet0/0</mark>

