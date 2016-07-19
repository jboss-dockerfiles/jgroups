# JGroups Gossip Router Docker Image

Starts a JGroups Gossip Router that acts as a lookup service.  
Cluster members register with under their cluster name, and new members query the GossipRouter for initial cluster membership information.

## Usage

To start and bind to localhost:12001

    docker run -p 12001:12001 jboss/jgroups-gossip

More at http://jgroups.org/javadoc/org/jgroups/stack/GossipRouter.html

