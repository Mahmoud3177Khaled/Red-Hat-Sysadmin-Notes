**Firewall Management:**
----------------------------------------------------------------------------------------------------------------
**firewalld** ---> Protects the machine from ingress traffic, based on activated allowed rules specifying ports, or plainly ports, or zones that provide a preset level of security.  

**systemctl status firewalld**  
**systemctl enable --now firewalld**  

**firewall-cmd** ---> Command to modify firewall rules.  

***A Zone is associated with various rules, services and ports that are allowed passage into the system***  

**firewall-cmd --list-all-zones** ---> See all available zones to make one active.  
**firewall-cmd --list-all** ---> Shows details of the currently active zone (Public is active by default).  

**ls /usr/lib/firewalld/services/** ---> Show all available rules for services in XML config files, allowed and unallowed ones.  

*But, when creating a new service to allow in a rule, make your edits in **"/etc/firewalld/services/custom-rule.xml"**, fill here with new custom rules for services as .xml files, that then can be allowed via:*  

**systemctl restart firewalld** ---> So it sees the newly created rule.  

**firewall-cmd --add-service=custom-rule --permanent** ---> Allowed this rule with its ports, but still need firewalld to be restarted for that rule to take effect.  
***--permanent*** makes sure that new rule is added to the permanent configuration of the zone under /etc/firewalld/zones/public.xml  

**systemctl restart firewalld**  
**firewall-cmd --list-all** and you see the new rule added and being applied.  

*Now the new ports are allowed :)*  
