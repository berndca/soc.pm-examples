# Example 1 - [Parallella EMMU: Memory translation Unit](https://github.com/parallella/oh/tree/master/src/emmu)


This is the state of the project **after** the dependencies have been fetched.
The dependencies are specified in the file soc.json in the root directory
of example1. They are:

- "parallella/oh/emmu": "~> 1.0"
- "openrisc/orpsoc-cores/verilog_utils": "~> 1.0", "only": "dev"

We require the emmu IP from parallella/oh with the latest available
version between 1.0 < version < 2.0 as well as verilog_utils in the same range.

The verilog_utils are requested to work around the lack of support for $clog2
in the icarus Verilog simulator. It's not needed for verilator or synthesis. 

The fetched IP RTL files and their IPXACT descriptions are stored below
the soc_lib directory. In addition to the explicitly specified dependencies
we find the files for packet2emesh and the library oh_lib. These were specified as dependencies 
inside the emmu package in soc_lib/emmu/soc.json.

The IPXACT files for the fetched IP are in the root directory of the IP directory tree:

- soc_lib/emmu/component.xml
- soc_lib/oh_lib/catalog.xml
- soc_lib/packet2emesh/component.xml
- soc_lib/verilog_utils/component.xml

The oh_lib structure deviates because it is a library and intended
to be used with the -y option during compilation. There are 69 modules in this library.
The component descriptions are in soc_lib/oh_lib/components/<name>.xml.
 
The file soc.lock in the root directory captures the currently installed versions and 
is used the achieve reproducible builds.
