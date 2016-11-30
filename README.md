# skydive-sdn-openshift
A mini tutorial to visualize to use Openstack Skydive project to visualize the Openshift SDN


## Create Project 
oc new-project network

## Give Rights to access sdn sockers (catch all, should fine tune)
oadm policy add-scc-to-user  privileged system:serviceaccount:$(oc project -q):default

## Daemon Set to deploy collector
oc label nodes --all sky-dive-collector=true

## Deploy Objects 
oc create -f https://raw.githubusercontent.com/ivanthelad/skydive-sdn-openshift/master/skydive-oscp.yaml


Browse to the Route endpoint and the visualizer should be available 
