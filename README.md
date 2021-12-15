# SocketExamples<br />
**Created Date:** 2/3/2010<br />
**Last Updated:** 10/15/2010<br />
**Description:** Client.dbl and Server.dbl are updated versions of code in the Synergy Language Reference Manual (LRM). These examples have been modified to present a more realalistic implementation of the Synergy Socket API. (Update for Synergy 9.5 compatibility)<br />
**Platforms:** Unix; OpenVMS<br />
**Products:** Synergy DBL<br />
**Minimum Version:** 8.1<br />
**Author:** William Hawkins
<hr>

**Additional Information:**
However, Synergy Language is single threaded, so implementing a Socket Server
that can respond to multiple clients concurrently is not possible. You can have
a server that acts as a listener and when a new client connects, launch a child
process that responds to the client requests. Each child only responds to a
single client. This technique is used in the RemoteBuild utility. This utility
can also be downloaded from the Synergy CodeExchange (http://www.synergyde.com).

Note, When using the -p option to alter the program logic to use SS_MSG_PEEK,
I have used a technique that places the message size in the first 4 bytes of the
message (in network byte order). This is not a requirement of SS_MSG_PEEK.
Also note, message acknowledgments do not use SS_MSG_PEEK technique.
