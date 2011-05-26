# Non responding applications

Whenever your application running on the Java Virtual Machine stops responding, before restarting them,
register these logs for future analysis (tested with Oracle/Sun implementation):

    jstack -F PID > hanging.jstack
    jmap -dump:live,format=b,file=hanging.jmap PID
    # or, if doesn't respond:
    jmap -dump:format=b,file=hanging.jmap -F PID


When running on a 64-bits machine, you may need to specify "-J-d64" option to both commands. The "-F" may be
unnecessary in some cases, but if the application doesn't respond, you can try using it. It is not
guaranteed that the application will be able to respond to jstack anyway.

For finding the PID of the application you can use ps:

    ps aux | grep application_name

# OUTPUT

The jstack output has a deadlock detection system, which has already pointed me some deadlocks
in the CometD Java library, so I know it can work sometimes.

TODO: Explain how to analyse these logs and present some tools like jhat and Netbeans integration.
