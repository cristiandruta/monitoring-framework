# monitoring-framework
Overview of the ATOM monitoring framework (installation, components, and documentation)

## Introduction
Reducing the energy consumption is a leading design constraint of current and future HPC systems. Aside from investing into energy-efficient hardware, optimizing applications is key to substantially reduce the energy consumption of HPC cluster. Software developers, however, are usually in the dark when it gets to energy consumption of their applications; HPC clusters rarely provide capabilities to monitor energy consumption on a fine granular level. Predicting the energy consumption of specific applications is even more difficult when the allocated hardware resources vary at each execution. In order to lower the hurdle of energy-aware development, we present ATOM---a light-weight neAr-real Time mOnitoring fraMework.


## Features
- Fundamental set of diverse plugins (from network monitoring over CPU performance to embedded system monitoring)
- Offers stable update rates for individual plugins of up to 20ms
- Agent-based architecture where a light-weight agents are installed on each target system to be monitored
- Each agent can be configured individually to report system-specific metric data
- Sophisticated RESTful service to allow data exchange: [API](https://excess-project.github.io/monitoring-server)
- Framework can be used stand-alone, in combination with the HPC resource manager TORQUE, or linked to the runtime system StarPU 


## Plugins
- Network monitoring: [infiniband](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/infiniband/README.md)
- Memory usage: [meminfo](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/meminfo/README.md)
- Embedded system support (Movidius): [movidius](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/movidius_arduino)
- Embedded system support (ACME): [acme](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/acme)
- Virtual memory statistics: [vmstat](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/vmstat/README.md)
- GPU support: [Nvidia GPUs](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/nvidia/README.md)
- Standard performance metrics: [PAPI-C](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/papi/README.md)
- Power and energy monitoring: [RAPL](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/rapl/README.md)
- CPU temperature data: [sensors](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/c/sensors/README.md)

For a more detailed introduction to plugins, please read our [introductory page](https://github.com/excess-project/monitoring-agent/blob/master/src/plugins/README.md).


## Get Started
Each component of the monitoring framework comes with its own setup and start scripts. Still, we also offer a convenient installation of a small testbed composed of three virtual machines (one server, two workers) by exploiting Vagrant and Ansible. For more information, please refer to our [README](https://github.com/excess-project/monitoring-setup-ansible/blob/master/README.md). If you should have all dependencies installed, a simple

```
git clone https://github.com/excess-project/monitoring-setup-ansible.git
cd monitoring-setup-ansible
vagrant up
```
starts the setup process.


## RESTful API
The API can be used to send and retrieve metric data to the monitoring database through the monitoring server. We have compiled a set of resources to get you up to speed:

- HTML-based [documentation](https://excess-project.github.io/monitoring-server)
- Sample API [clients](https://github.com/excess-project/monitoring-api) written in C and Python

