SystemD Container
========
Requires private key whose public key pair is in `authorized_keys` file of `<user>`
`<user>` must also have a passwordless sudo
-- sudo is not required if chroot/systemd container will be installed in a non privalged directory.
   -- path is chosen via `chroot_basepath` variable
   -- if you do not use sudo remove `-b --become-user root` from run command


---

Requirements
------------
- `ansible 2.4`

To log into container:
Substitute below with your variables from deploy.yml
Intial User is root, intial password is 1234 (CHANGE!)
`systemd-nspawn -bD <chroot_basepath>/<chrootname>`

`ansible-playbook -i hosts deploy.yml --private-key=<private-key> -u <user> -b --become-user root`
