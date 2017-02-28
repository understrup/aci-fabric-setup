#aci-fabric-setup
A python tool to set basic ACI fabric parameters according to a configuration file with the below format:	 											Configuraion file:

	{"aci fabric setup": {
		"Fabric date":{
		   "Infrastructure VLAN ID" = <vlan-id>
		   "Comment : a vlan only used in the fabric)" 
			"PODS":{
				"POD 1":{
					"Site pod name Name"	=	"<pod name>"
					"TEP ip-scope"	= <"x.y.z.w>"
					"Comment : TEP IP-Scope	a /16 that not can be reused in any of the other pods"
				}
			}
		}
		"ntp": {
			"Network Time Protocol"
   		 		"server 1": { 
      				"ip-addess"		=	"<x.y.z.w>"
      				"ipv6-address"	= 	"<x:y:z::w>"
      				"dns-name"		= 	"<dns-name>"
    			}
    			"server 2": { 
      				"ip-addess"		=	"<x.y.z.w>"
      				"ipv6-address"	=	"<x:y:z::w>"
      				"dns-name"		= 	"<dns-name>"
    			}
    			"server 2": { 
      				"ip-addess"		=	"<x.y.z.w>"
      				"ipv6-address"	= 	"<x:y:z::w>"
      				"dns-name"		= 	"<dns-name>"
    			}
    	}
    	
    }}	
																							 																								DNS													domain-name	domain-name	domain-name	domain-name																																NAME server ip address													ip-address   ipv6-address   dns-name	
	ip-address   ipv6-address   dns-name
		ip-address   ipv6-address   dns-name	
	ip-address   ipv6-address   dns-name								 												 												SNMP									 			 	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	Trap-destination																			 	Version	Version	Version	Version								 												 	Community	Community	Community	Community								 												 												 	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	Server address							 												 	Version	Version	Version	Version																					Community	Community	Community	Community																																Syslog													ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   																					Level	Level	Level	Level																																Tacacs													ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name																							tacacs key	tacacs key																																		VM-WARE													VMware Domain name 1	VMware Domain name 2	VMware Domain name 3	VMware Domain name 4																					vCenter IP  1   	vCenter IP 2      	vCenter IP  3 	vCenter IP  4   																					Datacenter Name 1	Datacenter Name 2	Datacenter Name 3	Datacenter Name 4																				