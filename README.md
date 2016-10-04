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
- Network monitoring: [infiniband](github/monitoring-agent/master/src/plugins/c/infiniband/README.md)
- Memory usage: [meminfo](github/monitoring-agent/master/src/plugins/c/meminfo/README.md)
- Embedded system support: [movidius](github/monitoring-agent/master/src/plugins/c/movidius_arduino)
- Virtual memory statistics: [vmstat](github/monitoring-agent/master/src/plugins/c/vmstat/README.md)
- GPU support: [Nvidia GPUs](github/monitoring-agent/master/src/plugins/c/nvidia/README.md)
- Standard performance metrics: [PAPI-C](github/monitoring-agent/master/src/plugins/c/papi/README.md)
- Power and energy monitoring: [RAPL](github/monitoring-agent/master/src/plugins/c/rapl/README.md)
- CPU temperature data: [sensors](github/monitoring-agent/master/src/plugins/c/sensors/README.md)

