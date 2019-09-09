* Commands useful dor determining the list of network interfaces 
  * ifconfig, netstat -i, ip link show
* Red Hat Linux tool for monitor permissions and ownership changes of critical files.
  * auditctl
* ifconfig resets traffic counters at 4Gb
* Identify new user's creation date and time
  * auth.log
* Ways to check for unexpected accounts:
  * /etc/passed and /etc/shadow, /etc/sudoers, /etc/groups
* /etc/pam.d PAM Pluggable authentication module. Checking for multifactor authentication configurations.
* Services are often started by xinetd (although newer versions of some distributions now use systemctl). 
  * For checking back doors associated with services go for /etc/xinetd.conf
* There is no common standard for determining the age of a user account in Linux. Some organizations add a comment to user accounts using the -c flag for user creation to note when they are created.