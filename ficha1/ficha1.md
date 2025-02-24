X = 50  N = 10

	***CONFIG R1
	ip address 192.168.X.254 255.255.255.0
	no shutdown

	exit

	service dhcp

	ip dhcp pool Grupo-N

	network 192.168.50.0 255.255.255.0

	default-router 192.168.50.1

	exit

	ip dhcp excluded-address 192.168.50.1 192.168.50.31 

	ip dhcp excluded-address 192.168.50.224 192.168.50.254

	end
***CONFIG PC1

ip dhcp

***CONFIG R1

ip dhcp pool Grupo-10                                 

dns-server 192.168.50.31 10.254.0.252

domain-name net-10.dei.uc.pt

netbios-name-server 10.1.0.253

lease 0 0 2

ip dhcp pool Grupo-10

host 192.168.50.17 255.255.255.0

client-identifier mac:address

client-name ns

default-router 192.168.50.1

domain-name se a stora quiser

dns-server 192.168.50.31

end
