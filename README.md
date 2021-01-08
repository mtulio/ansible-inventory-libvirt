# ansible-inventory-libvirt

Ansible Dynamic Inventory for Libvirt

## Proposal

Script to gather data from Libvirt and export to ansible as dynamic inventory source.



### Directory structure

src/ # 
- module of libvirt program

bin/ 
- keeps CLI command to resides inside the inventory directory. It can auto generate the 
inventory script based on each domain source. Eg. you can keep two different source discovery 
based on an configuration file.
- ansible-inventory-libvirt



Samples

~~~
python ansible-inventory-libvirt --list
{
    "_meta": {
        "hostvars": {
            "centos8": {
                "ansible_host": "192.168.122.96",
                "iface": "virbr0"
            },
            "rhce-control": {
                "ansible_host": "192.168.122.169",
                "iface": "virbr0"
            }
        }
    },
    "all": {
        "children": [
            "ungrouped"
        ]
    },
    "ungrouped": {
        "hosts": [
            "localhost"
        ]
    },
    "virt": {
        "hosts": [
            "centos8",
            "ansible-control"
        ]
    }
}

~~~
