#aci-fabric-setup version 0.01
A tool to configure basic ACI fabric parameters like NTP, DNS, SNMP, SYSLOG, TACACS and VMware connecter.
##Tool input paramenters

###aci-fabric-setup \<apic-url> \<user-id> \<password> \<configuration file>##Python imports
import argparse  
import os##ACI fabric parameters is set according to a configuration file with the below format:
###Configuraion file:

	{"aci fabric setup" : {
		"Fabric date" : {
		   "Infrastructure VLAN ID" = "<vlan-id>"
		   		"Comment : a vlan only used in the fabric)"
		   	"Internal-fabric-as-number" = "<as-number>" 
			"PODS" : {
				"POD" : {
					"POD-No"		= "<1-12>"
					"POD-Name"		= "<pod name>"
					"TEP-ip-scope"	= "<x.y.z.w>"
						"Comment : TEP IP-Scope a /16 that not can be reused in any of the other pods"
					"Multipod-IPN" : {
						"OOB-IPN01-ip-addess/ipv6-address"	= "<x.y.z.w/q>/<x:y:z::w/q>"
						"OOB-IPN02-ip-addess/ipv6-address"	= "<x.y.z.w/q>/<x:y:z::w/q>"
						"IPN0x-to-spine1-interface			= "<interface nane ex, e1/12>"
						"IPN0x-to-spine2-interface"			= "<interface nane ex, e1/12>"
					} 
				} : Above line is repeated per pod-to-pod links"
			}
			"Multipod" :	{
			  	"mulitipod-as-number" = "<as-number>" 
				"capacity-between-pods" : { 
					<"Pod-x"> = <"Pod-y"> = <"capacity per link same internal link speed in all pods">
						"<x>"	=	"<y>"	= 	<"capacity per link">
						"Above line is repeated per pod-to-pod links"
				} "Comment : Delete above line if multipod is not used"
			}
		}
		"ntp": {
			"Network Time Protocol"
				"server" : { 
      				"ip-addess/ipv6-address/dns-name" 	= "<x.y.z.w>/<x:y:z::w>/dns-name"
      				"primary ntp server"                = "<prefed>"
      		} : "A server section is added per ntp server"
     	}
		"DNS": {
			"Domain-name" : {
				"Domain-name" = "<domain nane>"
			} : "A domain-name section is added per domain name"
			"Name server ip address": { 
      				"ip-addess/ipv6-address" = "<x.y.z.w>/<x:y:z::w>"
    		} : "A server section is added per DNS server"
    	}
    	"SNMP": {
			"server": { 
      			"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
    		}: "A server section is added per snmp server"
			"Trap destination": {
      				"ip-addess/ipv6-address/dns-name" 	= "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if Destination due not exist"
					"Version"							= "<2c/3>"
					"Community"							= "<Commnuity name>"
    		} : "A server section is added per trap destination"
    	}
		"Syslog": {
			"server": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Level"								= "<0-7>"
    		} : "A server section is added per syslog server"
    	}
		"Tacacs": {
			"server": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Key"								= "<tacacs key>"
    		} : "A server section is added per Tacacs server"
    	} 
		"MCP":	{
			"Comment :  Mis-Cabling Protocol" 
			"MCP"			= "<enable/disable>"
			"Key"			= "<text string>"
				"Comment : The key or password to uniquely identify the MCP packets within this fabric."
			 "MCP_per_vlan"	= "<enable/disable>"
		}
		"Port_Tracking":	{
				"Comment : if all aci-uplink ports on a leafs is down all down-links ports are closed."
			"Mode"	= "<enable/disable>"
		}
		"EP_loop_protection" : {
				"Comment : In cause for an end-point loop the interface is closed.."
			"Mode"	= "<enable/disable>"
		}
		"Error_Disabled_Recovery_Policy"	: {
				"Comment : 	The error disabled recovery policy specifies the policy for re-enabling"
				"			a port that was disabled due to one or more pre-defined error conditions."
			"Mode"	= "<enable/disable>"
		}
 		"APIC_QoS_Preservation"	 : {
				"Comment :	The ACI fabric is an 802.1p-COS based and the interpod-network ip network"
				"			are based on RFC4594. Enable marks 802.1p to DCSP arcording to RFC4594"
			"Mode"	= "<enable/disable>"
		}	
		"VM-Ware": {
			"vmware connecter": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"VMware Domain name"				= "<vmware domain name>"
					"VMware Datacenter name"			= "<vmware datacenter name>"
					"Key"								= "<vmware key>"
    		}
    	}
    }
    
    


