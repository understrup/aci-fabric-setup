#aci-fabric-setup
A python tool to set basic ACI fabric parameters according to a configuration file with the below format:	 											Configuraion file:

	{"aci fabric setup": {
		"Fabric date":{
		   "Infrastructure VLAN ID" = <vlan-id>
		   "Comment : a vlan only used in the fabric)" 
			"PODS":{
				"POD 1":{
					"Site pod name Name"	=	"<pod name>"
					"TEP ip-scope"			=	<"x.y.z.w>"
						"Comment : TEP IP-Scope	a /16 that not can be reused in any of the other pods"
				}
				"POD 2":{
					"Site pod name Name"	=	"<pod name>"
					"Comment : Left empty if pod due not exist"
					"TEP ip-scope"			=	<"x.y.z.w>"
				}
				"POD 3":{
					"Site pod name Name"	=	"<pod name>"
						"Comment : Left empty if pod due not exist"
					"TEP ip-scope"			=	<"x.y.z.w>"
				}
				"POD 4":{
					"Site pod name Name"	=	"<pod name>"
						"Comment : Left empty if pod due not exist"
					"TEP ip-scope"			=	<"x.y.z.w>"
				}
				"POD 5":{
					"Site pod name Name"	=	"<pod name>"
						"Comment : Left empty if pod due not exist"
					"TEP ip-scope"			=	<"x.y.z.w>"
				}
			}
		}
		"ntp": {
			"Network Time Protocol"
   		 		"server 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
    			}
    			}
    	}
		"DNS": {
			"Domain-name":{
				"Domain-name 1" = "<nane1>"
				"Domain-name 2" = "<nane2>"
					"Comment : Left empty if domain due not exist"
				"Domain-name 3" = "<nane3>"
					"Comment : Left empty if domain due not exist"
				"Domain-name 4" = "<nane4>"
					"Comment : Left empty if domain due not exist"
			}
			"Name server ip address"
   		 		"server 1": { 
      				"ip-addess/ipv6-address" = "<x.y.z.w>/<x:y:z::w>"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address" = "<x.y.z.w>/<x:y:z::w>"
						"Comment : Left empty if server due not exist"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address" = "<x.y.z.w>/<x:y:z::w>"
						"Comment : Left empty if server due not exist"
    			}
    	}
    	
    }}	
																			 												 												SNMP									 			 	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name	Trap-destination																			 	Version	Version	Version	Version								 												 	Community	Community	Community	Community								 												 												 	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	Server address							 												 	Version	Version	Version	Version																					Community	Community	Community	Community																																Syslog													ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   	ip-address   ipv6-address   																					Level	Level	Level	Level																																Tacacs													ip-address   ipv6-address   dns-name	ip-address   ipv6-address   dns-name																							tacacs key	tacacs key																																		VM-WARE													VMware Domain name 1	VMware Domain name 2	VMware Domain name 3	VMware Domain name 4																					vCenter IP  1   	vCenter IP 2      	vCenter IP  3 	vCenter IP  4   																					Datacenter Name 1	Datacenter Name 2	Datacenter Name 3	Datacenter Name 4																				