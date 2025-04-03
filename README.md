# network-devops
Operaciones de networking

'''vim /etc/udev/rules.d/70-persistent-net.rules

```export ENS160=`ip a | grep link.ether | cut -c16-32 | head -n1`

```sed -Ei "s/(ATTR\{address\}==\")[0-9A-Fa-f:]+(\", NAME=\"ens160\")/\1$ENS160\2/" /etc/udev/rules.d/70-persistent-net.rules

```udevadm control --reload-rules

```udevadm trigger

```ip link show
