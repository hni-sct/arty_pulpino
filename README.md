<img src="https://raw.githubusercontent.com/pulp-platform/pulpino/master/doc/datasheet/figures/pulpino_logo_inline1.png" width="400px" />

# FPGA Synthesis

## Requirements
You need [Xilinx Vivado](https://www.xilinx.com/support/download.html) installed in `/opt/Xilinx/`. We testet the flow with Vivado 2018.2 and Ubuntu 20.04.2.0.

## Quickstart
Make Vivado available in the commandline
```
$ source /opt/Xilinx/Vivado/2018.2/settings64.sh
```

Clone this repository
```
$ git clone https://github.com/hni-sct/arty_pulpino.git
$ cd arty_pulpino/ && ./update-ips
```
Start the flow

```
$ cd arty_pulpino/fpga
$ make -f Makefile.arty clean
$ make -f Makefile.arty arty_top
```

The flow may fail the first time you run it. If this is the case, just run
```
$ make -f Makefile.arty arty_top
```
as second time.

The bitstream can now be found in `arty_pulpino/fpga/arty_top/arty_top.bit`.

# Important Files

- FPGA shell (top module) can be found in `arty_pulpino/fpga/rtl/arty_top.v`
- Generated Xilinx IPs can be found in `arty_pulpino/fpga/ips`
- XDC file can be found in `arty_pulpino/fpga/arty_top`
- TCL scripts can be found in `arty_pulpino/fpga/arty_top/tcl` for the FPGA shell
  and in `arty_pulpino/fpga/arty_pulpino/tcl` for the Pulpino.
