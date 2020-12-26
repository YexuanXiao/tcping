tcping - ping over a tcp connection for Windows
--------------------------------------------------------------

Usage: tcping [-flags] server-address [server-port]

tcping [-t] [-d] [-i interval] [-n times] [-w ms] [-b n] [-r times] [-s] [-v] [-j] [-js size] [-4] [-6] [-c] [-g count] [-S source_address] [--file] [-o filename] [-h] [-u] [--post] [--head] [--proxy-port port] [--proxy-server server] [--proxy-credentials username:password] [-f] server-address [server-port]

 -t     : ping continuously until stopped via control-c

 -n 5   : for instance, send 5 pings

 -i 5   : for instance, ping every 5 seconds

 -w 0.5 : for instance, wait 0.5 seconds for a response

 -d     : include date and time on each line

 -b 1   : enable beeps (1 for on-down, 2 for on-up,
                        3 for on-change, 4 for always)

 -r 5   : for instance, relookup the hostname every 5 pings

 -s     : automatically exit on a successful ping

 -v     : print version

 -j     : include jitter, using default rolling average

 -js 5  : include jitter, with a rolling average size of (for instance) 5.

 -o     : print console to a file, filename after '-o'

 --append : Append to the -o filename rather than overwriting it

 -4     : prefer ipv4

 -6     : prefer ipv6

 -c     : only show an output line on changed state

 --file : treat the "server-address" as a filename instead, loop through file line by line

          Note: --file is incompatible with options such as -j and -c as it is looping through different targets

          Optionally accepts server-port.  For example, "example.org 443" is valid.

          Alternately, use -p to force a port at command line for everything in the file.

 -g 5   : for instance, give up if we fail 5 times in a row

 -S _X_ : Specify source address _X_.  Source must be a valid IP for the client computer.

 -p _X_ : Alternate method to specify port

 --fqdn : Print domain name on each line if available

 --ansi : Use ANSI color sequences (cygwin)

 --color: Use Windows color sequences


HTTP Options:

 -h     : HTTP mode (use address without http://)

 -u     : include target URL on each line

 --post : use POST rather than GET (may avoid caching)

 --head : use HEAD rather than GET

 --proxy-server : specify a proxy server

 --proxy-port   : specify a proxy port

 --proxy-credentials : specify 'Proxy-Authorization: Basic' header in format username:password


Debug Options:

 -f     : force tcping to send at least one byte

 --header : include a header with original args and date.  Implied if using -o.

 --block  : use a 'blocking' socket to connect.  This prevents -w from working and uses the default timeout (as long as 20 seconds in my case).  However it can detect an actively refused connection vs a timeout.