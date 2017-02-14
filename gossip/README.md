# JGroups Gossip Router Docker Image

Starts a JGroups Gossip Router that acts as a lookup service.  
Cluster members register with under their cluster name, and new members query the GossipRouter for initial cluster membership information.

## Usage

To start and bind to localhost:12001

    docker run -p 12001:12001 jboss/jgroups-gossip

More at http://jgroups.org/javadoc/org/jgroups/stack/GossipRouter.html

### Logging

The image uses log4j2 for logging. The level of the logger ```org.jgroups``` is configurable using a system property. To run with TRACE enabled:

```
docker run -it -e "LogLevel=TRACE"  jboss/jgroups-gossip
```


It's also possible to use a different log4j2.xml file altogether. To specify a different conf file, from a mounted volume:

```
docker run -it -e "LOG4J2_FILE=/mount/folder/log4j2.xml" -v /local/folder:/mount/folder jboss/jgroups-gossip
```
