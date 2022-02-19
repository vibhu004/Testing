# How to flush the DHCP server lease cache

> Check you /var/lib/dhcpd/dhcpd.leases files and check for the entry. It contains the list of all dhcp servers.

### Step 1 : Stop dhcp server
`service dhcpd stop` <br>
`systemctl stop dhcpd`

### Step 2 : Delete the temporary file dhcpd.leases
`rm dhcpd.leases`

### Step 3 : Flush the lease cache dhcpd.leases
`echo "" > dhcpd.leases`

### Step 4 : Start DHCP Server
`service dhcpd start` <br>
`systemctl start dhcpd`

> The next time the clients will request a lease they will probably obtain a different IP respect the one they had before