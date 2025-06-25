# About your node


!!! warning "This guide is incomplete"

    We need to add photos of the different kinds of routers and
 

## How does it work?

Tucson Mesh gets bandwidth directly from an internet exchange point (IXP) and distributes it wirelessly through rooftop antennas. When you join Tucson Mesh, you and other members of Tucson Mesh will install a wireless router on your rooftop.

The rooftop router setup connects you to our network and the broader internet. It will also broadcast throughout your neighborhood. This makes it easier for your neighbors to join and strengthens Tucson Mesh.

## So what’s on my roof?

Each of our installs needs to connect the user’s home back to one of the main hubs of our network, and from there, the larger internet. We call our main hubs the [“supernodes”](../../networking/supernodes/index.md) of Tucson Mesh. Our first supernode is located at the [BICAS](../../networking/supernodes/bicas.md), and in mid-2025, we brought a second supernode atop [Tucson House](../../networking/supernodes/tucson-house.md) online. If your rooftop has a line of sight to the antenna mast of a supernode, you can connect to the supernode via an antenna pointed directly at the supernode. Alternately, you can use another antenna to connect with a neighbor’s rooftop antenna that can be seen from your roof.

### Connecting directly to the supernode

For connecting directly to the supernode, we currently use the [Ubiquiti LiteBeam 5 AC Gen 2](../../hardware/litebeam.md), a router with an integrated directional antenna (meaning it sends and receives wireless data through the air in a straight line).

### Connecting to a neighbor's node

At a typical install, we include another router that plugs into the LiteBeam via an ethernet cable. This is a router with an integrated omnidirectional antenna, meaning that it broadcasts a signal in a 360 degree radius. We use the [MikroTik OmniTIK 5 PoE AC](../../hardware/omnitik.md) for this.

The inclusion of the OmniTIK allows for connections between neighboring nodes. If a particular node doesn't have a line of sight to a supernode, its OmniTIK can still connect to a neighboring node. Your connection can than route through that node's LiteBeam and on to the supernode and internet. Or, it could hop through another neighboring node.

The OmniTIK on your roof also creates an open 5Ghz WiFi network that is broadcast in all directions and named `Tucson Mesh Free Wifi`. This network allows people passing your house on the street to use the Mesh for free, and also let's people know about the project.

## What's in your home?

In addition to the rooftop routers, you'll typically have a router inside your home to provide a wireless network for your household. Often, we'll use something like a [TP-Link Archer C7 AC1750 Wireless Dual Band Gigabit Router](../../hardware/tp-link-ac1750.md) for this purpose.

## The routers work together

At a typical install with both an OmniTIK and a LiteBeam, the OmniTIK draws power through an ethernet cable from a power over ethernet (PoE) injector that is plugged into a wall socket inside your house. The OmniTIK then passes on power to the LiteBeam via a short ethernet cable that connects the two routers. 

Once the LiteBeam is powered on, it connects to the supernode and starts to transmit and receive data, which passes to the OmniTIK and then to your indoor router.

The mesh is configured so that if your LiteBeam's connection to the supernode goes down, your OmniTIK will continue to try to connect to the internet through any neighboring OmniTIKs that it can reach. The more nodes we include in the network, the more resilient and reliable Tucson Mesh becomes.

## What happens when I leave the mesh network?

If you move or if you no longer want to be a part of the mesh network, we ask that you contact us through the [#user-support](https://tucsonmesh.slack.com/archives/C03P19L1WBF) Slack channel, or send an email to [support@tucsonmesh.net](mailto:support@tucsonmesh.net) and ask someone to come get the hardware from your home.

