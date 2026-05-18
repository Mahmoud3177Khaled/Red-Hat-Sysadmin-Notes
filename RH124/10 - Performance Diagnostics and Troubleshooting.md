**Performance Diagnostics and Troubleshooting:**  
----------------------------------------------------------------------  

**free -m** ---> See systems memory details now.  

**lscpu** ---> cpu information  
**lscpu | grep "^cpu(s)"** ---> How many cpu cores available on this system.  

**nproc** ---> Print number of cpu cores the system has.  

**uptime** ---> See system up time, # of logged users,   
	AND: CPU loads in past 1, 5 and 15 mins  

		-- For each of them, devide by how many cpus exist and if:
				- *Greater than 0* = You have processes that want to run that exceed the system's resources.
				- *Equal/close to 0* = You have barely enough resources for the demand
				- *Less than 0*= You have way too little utilization for your resources


**df -h [/]**---> Shows disk utilization information  
**du -sh <directory>**---> Shows how big a a folder is on disk  

**netstat -plunt**---> Shows all currently opned ports along with the processes running using them  
**ss -plunt**---> Same as netstat, but faster and more modern.  

and of course: **top** and **htop**  


**journalctl -f**---> See and search in system logs in a pager live as they appear.     ***(and -r for most recent to be up-top)***  
**journalctl -u httpd**---> to see a certain systemd service logs.  

**journalctl --since "2026-05-1 12:00:00" --until "2026-05-1 13:00:00"** -->  See logs falling in that timeframe  

**journalctl --disk-usage** --> Know how much storage you jornal is taking.  
**journalctl --vacuum-time=2d** --> To clear the journal upto a certain age.  

**dmesg**---> Shows hardware device messages and OS boot logs  

**Red Hat/Rocky web console** ---> the cockpit .service runs can be accessed by **http://IP:9090** Like:  https://10.248.149.129:9090  
