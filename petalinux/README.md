
## PetaLinux recipe for plversion module

- copy project-spec directory to PetaLinux project directory

```cp -a project-spec <petalinux_proj_dir>```

- append ```CONFIG_plversion```  to ```meta-user/conf/user-rootfsconfig```

- run ```petalinux-config``` and select ```plversion``` in ```mdoules```

- build PetaLinux with ```petalinux-build```
