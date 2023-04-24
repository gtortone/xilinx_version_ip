# xilinx_version_ip
Simple IP that exposes build date and time, version control, and version information

Adding the compilation date is very useful to verify that the correct firmware is running. This
is a method add the compilation date and time on firmware and allow the user to read it
back from the zynq processor.

The method is described here https://blog.reds.ch/?p=1208 and the source files are here
https://github.com/rick-heig/xilinx_version_ip.

The basic idea is to have a set of generics in the top level file that are a sort of placeholders
for the compilation data and time and git hash that are updated by means of a TCL script
that start automatically when the synthesis is started in vivado. Then these generics are
passed to a block connected to the processor bus and read back via a command in
baremetal or Linux.

This driver will instantiate four read-only attributes in the sysfs and these files can be used to retrieve the values.

The device entry is created under ```/sys/bus/platform/devices/``` . The name is taken from the device tree entry (and therefore also contains the address).

The attribute files can be read from there in order to obtain the values.
