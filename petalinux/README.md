
## PetaLinux recipe for plversion module

- copy project-spec directory to PetaLinux project directory

```cp -a project-spec <petalinux_proj_dir>```

- append ```CONFIG_plversion```  to ```meta-user/conf/user-rootfsconfig```

- run ```petalinux-config -c rootfs``` and select ```plversion``` in ```modules```

- edit ```project-spec/meta-user/recipes-bsp/device-tree/files/system-user.dtsi``` and add an overlay with correct ```compatible``` property:

```
&version_ip_v1_0 {
   compatible = "xlnx,version-ip-1.0";
};
```

- build PetaLinux with ```petalinux-build```
