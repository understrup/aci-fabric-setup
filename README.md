#aci-fabric-setup
A python tool to set basic ACI fabric parameters according to a configuration file with the below format:

	{"aci fabric setup": {
		"ntp": {
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
												
	ip-address   ipv6-address   dns-name
		ip-address   ipv6-address   dns-name	
	ip-address   ipv6-address   dns-name								 