# nagios-bash-plugin-f5-SSL-TPS-via-SNMP

This is bash script can be used as a Nagios plugin to check SSL transactions per second on a given LTM using SNMP.

The value produced by this script is calculated over a time interval as "SSL Transactions per Second" are not directly available as a value from a SNMP query.

Note: levels of "SSL Transactions per Second" on a f5 may be a licensed feature and potentially capped.

Testing:
You can run this check by hand like this:
./check_snmp_f5ltm_tps <hostname or ip> <snmpv2 community secret> <interval in seconds>
i.e. $ ./check_snmp_f5ltm_tps 192.168.1.20 secret 10

Instructions:
0. Put the script and configs in the appropriate Nagios locations.
1. Configure the cfgs to your contact groups, host groups and sample interval.
2. The script to be executable, "chmod +x check_snmp_f5ltm_tps"
3. Check your nagios config and then reload nagios.

To Do:
- get_opts
- perfomance gathering/metrics
- turn TPS levels to variables for nagios return states
