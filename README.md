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
			"PODS" : {
				"POD" : {
					"POD-No"			= "<1-12>"
					"POD-Name"		= "<pod name>"
					"TEP-ip-scope"	= <"x.y.z.w>"
						" Comment : TEP IP-Scope a /16 that not can be reused in any of the other pods"
				"Multipod-IPN-OOB"
					"IPN01-ip-addess/ipv6-address" = "<x.y.z.w/q>/<x:y:z::w/q>"
					"IPN02-ip-addess/ipv6-address" = "<x.y.z.w/q>/<x:y:z::w/q>"
					"IPN01-to-spine1-interface" = "<interface nane ex, e1/12>"
					"IPN01-to-spine2-interface" = "<interface nane ex, e1/12>"
					"IPN02-to-spine1-interface" = "<interface nane ex, e1/12>"
					"IPN02-to-spine2-interface" = "<interface nane ex, e1/12>"
				} 
			}
			"Multipod" :	{
				"capacity-between-pods" 
					"1-1"	:	<"capacity per link same internal link speed in all pods">
					"1-2"	:	<"capacity per link">
					"1-3"	:	<"capacity per link">
					"1-4"	:	<"capacity per link">
					"2-3"	:	<"capacity per link">
					"2-4"	:	<"capacity per link">
					"3-4"	:	<"capacity per link">
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
			"Name server ip address"
   		 		"server": { 
      				"ip-addess/ipv6-address" = "<x.y.z.w>/<x:y:z::w>"
    			} : "A server section is added per DNS server"
    	}
		"SNMP": {
			"Simple Network Management Protocol"
   		 		"server": { 
      				"ip-addess/ipv6-address/dns-name" = "<x.y.z.w>/<x:y:z::w>/dns-name"
    			}
    		} : "A server section is added per snmp server"
			"Trap destination"
    			"Destination": { 
      				"ip-addess/ipv6-address/dns-name" 	= "<x.y.z.w>/<x:y:z::w>/dns-name"
						"Comment : Left empty if Destination due not exist"
					"Version"							= "<2c/3>"
					"Community"							= "<Commnuity name>"
    			} : "A server section is added per trap destination"
		"Syslog": {
   		 		"server": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Level"								= "<0-7>"
    			} : "A server section is added per syslog server"
		"Tacacs": {
   		 		"server": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"Key"								= "<tacacs key>"
    			} : "A server section is added per Tacacs server"
   		} 
		"VM-Ware": {
   		 		"vmware connecter": { 
      				"ip-addess/ipv6-address/dns-name"	= "<x.y.z.w>/<x:y:z::w>/dns-name"
					"VMware Domain name"		= "<vmware domain name>"
					"VMware Datacenter name"	= "<vmware datacenter name>"
					"Key"						= "<vmware key>"
    			}
    	
    }}	

