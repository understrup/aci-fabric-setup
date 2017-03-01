#aci-fabric-setup version 0.01
A python tool to set basic ACI fabric parameters.##Tool input paramenters

###aci-fabric-setup \<apic-url> \<user-id> \<password> \<configuration file>##ACI fabric parameters is set according to a configuration file with the below format:
###Configuraion file:

	{"aci fabric setup": {
		"Fabric date":{
		   "Infrastructure VLAN ID" = <vlan-id>
		   "Comment : a vlan only used in the fabric)" 
			"PODS":{
				"POD 1":{
					"Site pod name Name"	=	"<pod name>"
					"TEP ip-scope"			=	<"x.y.z.w>"
						" Comment : TEP IP-Scope	a /16 that not can be reused in any of the other pods"
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
		"SNMP": {
			"Simple Network Management Protocol"
   		 		"server 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
    			}
    			"server 3": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
    			}
    		}
			"Trap destination"
    			"Destination 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if Destination due not exist"
					"Version"						= "<2c/3>"
					"Community"						= "<Commnuity name>"
    			}
    			"Destination 2": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if Destination due not exist"
					"Version"						= "<2c/3>"
					"Community"						= "<Commnuity name>"
    			}
    			"Destination 3": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if Destination due not exist"
					"Version"						= "<2c/3>"
					"Community"						= "<Commnuity name>"
    			}
		"Syslog": {
   		 		"server 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Level"	= "<0-7>"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
					"Level"	= "<0-7>"
    			}
    			}
    			"server 3": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
					"Level"	= "<0-7>"
    			}
		"Tacacs": {
   		 		"server 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Key"	= "<tacacs key>"
    			}
    			"server 2": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if server due not exist"
					"Key"	= "<tacacs key>"
    			}
    			}
		"VM-Ware": {
   		 		"vmware connecter 1": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
					"VMware Domain name"	=	"<vmware domain name>"
					"VMware Datacenter name"	=	"<vmware datacenter name>"
					"Key"	= "<vmware key>"
    			}
    	
    }}	

