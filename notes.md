
# QuickStart

Startup developping env detached - `docker compose --profile dev up -d`

Interactive terminal - `docker compose exec dev bash`

Copmile and deploy code to the orin - `docker compose --profile target up`


Pretty sure you can connect vscocde conatainers to this. 

# Fluff

1. opencv-pythondoes not support cuda operations. It is CPU ONLY(which is bad because orin is a cuda board)


First will be x86 for a dev. We will try to abstract as much as possible so that when we deploy  
to orin with the target tag, it can correctly apply its own optimisations and compat layers. 

BTW keep in mind, memory in orin is uniform(CPU & GPU share the same mem space) so try to reduce the amount of unneccessary copies. 


Troubleshoot:
1. If nvidia drivers are not initialised, i.e not installed running and a cuda device is not detected, the container crashes.

For SpeedyBee it needs speciifc usb serial access. 
1. MAVLINK for ardupilot
2. 
