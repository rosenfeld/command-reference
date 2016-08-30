# Using socat to implement a simple HTTP service to display the client's IP

Useful when testing forwarding rules:

    socat -T 0.5 TCP-L:10081,reuseaddr,fork,crlf SYSTEM:"echo TP/1.0 200; echo Content-Type\: text/plain; echo; echo \$SOCAT_PEERADDR;echo"

This will listen on port 10081 with a timeout of 0.5s to close the connection.
