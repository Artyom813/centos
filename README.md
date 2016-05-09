Hetzner Install CentOS 7.2 minimal image
=========

Install Hetzner Server from Rescue System with Ansible

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Install Hetzner Server
        hosts: node14X

        roles:
            - role: hetzner-install
            binary: /root/.oldroot/nfs/install/installimage
            boot_loader: grub
            raid:
                active: 'no'
                level: 0
            disks:
                - sda
                - sdb
            image: /root/images/CentOS-72-64-minimal.tar.gz
            partitions:
                - /boot:ext3:512M
                - lvm:vg0:all
            logical_volumes:
                - vgos:root:/:ext4:30G
                - vgos:var:/var:ext4:900G
            format_second: 'no'
            hostname: node14X
            key_url: https://gist.githubusercontent.com/asdasd.txt
