while installing Linux its important to know Linux are installed in hypervisor and what is hypervisors 

  

# Hypervisor


A hypervisor (or Virtual Machine Monitor, VMM) is software that lets multiple operating systems run on a single physical machine. It manages hardware resources (CPU, memory, storage) and allocates them to virtual machines (VMs) without interference. This improves hardware utilization, reduces costs, and provides flexibility in cloud and server environments. Its primary roles is to manage virtual machines

### How It Works

A hypervisor runs on hardware or a host OS to create and manage virtual machines (VMs), each with its own virtual CPU, memory, storage, and network. It intercepts guest OS requests and translates them to physical hardware, ensuring isolation, security, and stability.

![419337647](https://media.geeksforgeeks.org/wp-content/uploads/20251208094155761752/419337647.webp "Click to enlarge")

Hypervisor are divided into two types
- Type 1 Hypervisor
- Type 2 Hypervisor
# Type 1 Hypervisors 

A Type 1 Hypervisor run directly on hosts hardware.it interact with hardware directly
. it offer better performance and security.
it is the standard for the enterprise level data centers too

# Type 2 Hypervisors 

A Type 2 Hypervisor run as an application within host OS . This type id generally used for the desktop virtualization, development, and testing environments where a user needs to run multiple OS on their personal computer . it is slower then type 1 hypervisor.




mac has .dmg and window has .exe package for virtual machine installation
installer image use .iso
 virtual machine image uses .ova for virtual box and .ovf for VMware. there are pre configured.virtual box need guest addition for full screen support
 


