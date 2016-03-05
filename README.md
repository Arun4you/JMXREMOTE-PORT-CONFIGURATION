# JMXREMOTE-PORT-CONFIGURATION
JMX ports are used to monitor the JVM using JVisualVM,Jconsole and other monitoring tools

JVM Parameters:

 -Dcom.sun.management.jmxremote.port= {port number} eg:7500
 -Dcom.sun.management.jmxremote.authenticate=false/true
 -Dcom.com.sun.management.jmxremote.password=file:///{path}/jmxremote.password 
 -Dcom.com.sun.management.jmxremote.access.file=file:///{path}jmxremote.access 
 -Dcom.sun.management.jmxremote.ssl=false/true

Go to MW_HOME/jdkversion/jre/lib/management. Then, create a copy of the jmxremote.password.template file and rename it to jmxremote.password.

By default, the user name monitorRole allows JConsole MBean read-only permissions, while the user name controlRole allows for full JMX MBean control. The following step explains how to change these default permissions.

To set permissions for each set of credentials, open the jmxremote.access file, located in the same directory, for editing. Then, use the keywords readonly and readwrite to specify the access level for each set of credentials. For example:

jmxremote.access file:

username1 readonly
username2 readwrite

jmxremote.password file:

username1 password1
username2 password2

Make sure to add permissions for any new credentials you added to the jmxremote.password file.

Because the jmxremote.password file contains passwords in clear text, you need to restrict access to this file to the file owner by changing the file access permissions, as follows:

On UNIX: Run the command chmod 600 jmxremote.password 


