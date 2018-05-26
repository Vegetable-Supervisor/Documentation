# Overview
Description of the project's components.

## Components
The project relies on three major components to work.


### Greenhouse
The greenhouse is the main component of the project.
Our goal is to facilitate its maintenance, and the other components exists for this sole purpose.
An installed greenhouse must be plug-and-play.

A greenhouse has to follow a specification in order to be compatible with the other systems.
In detail, it has to implement :
- a SSDP service that will respond to service discovery targeted at greenhouses
- a HTTP JSON RPC API for delivering information (e.g. picture, temperature...) to the Supervisor.

### Supervisor
The supervisor is the component that should be connected to every greenhouses to provide a unified interface to the user. The user does not directly interface with the greenhouses, but manages them on the supervisor's website.
Any necessary user configuration should be made through this website.

Support for multiple supervisors is considered for later.

### Wi-Fi Router
The Wi-Fi router provides the missing link between the greenhouses and the supervisor.
The supervisor is directly connected to the router with a physical link.
The greenhouses connects to the router's Wi-Fi. The Wi-Fi network must encrypt data (e.g. using WPA2), since the communication between a greenhouse and the supervisor is in clear text (HTTP).

Because of the encrytion, a setup is required for greenhouses (e.g. setup the pre-shared key). This should be done by the controller, for example by setting up the image of the greenhouse (automating any configuration), and then letting the user setting up the image on the greenhouse physically.

A limitation is that greenhouses outside of the Wi-Fi range may not be able to be used.

The router must implement a DHCP server if IPv4 is used.

## Protocol overview
This section describes the two main protocols used for greenhouse-supervisor communication.

### Service Discovery

### HTTP RPC API
