# Guides
1. Server Network Configuration  
- RedPlane provides a default configuration plane using `netplan` [here](./01-netcfg.yaml).
Instead of using the default `NetworkManager`, it uses `networkd` to create two NIC, one with DHCP, another one with static IPs and routes.  
- Put the file under the directory `/etc/netplan/`.
- Apply the network
  - Before apply the new network configuration, you may want to backup your previous one if there are any.
  - Test the configuration with `sudo netplan try`
  - Apply the configuration with `sudo netplan apply`
- Mostly the Redplane would only use the `ens1` interface, it seems that `eno5` is just a backup for previous network.
2. Enable Performance mode on servers
- This one-line [script](./cpu_performance.sh) helps the server achieve maximum performance.
3. Install MLNX_OFED Driver remotely
- Install the MLNX_OFED driver with the [script](./install_mlnx_ofed_all.py) it provides, also as a reference you can take a look at the offical [docs](https://enterprise-support.nvidia.com/s/article/howto-install-mlnx-ofed-driver).
> TODO: It seems there are multiple end-hosts in the script, figure out what are these entites.
4. 