# core/lib

This repository contains common modules instantiated by other cores:

* **lowlevel** contains modules for math operations (addition, subtraction, etc). Two sets of modules are provided: **generic** ones can be used during simulation and when porting to a different architecture, modules from **artix7** should be used when building a bitstream for the Alpha board. To use the modules first `` `include "cryptech_primitive_switch.vh"``, then instantiate them using `` `CRYPTECH_PRIMITIVE_*`` macro.

* **memory** contains wrappers for block memories:
    * ``bram_1rw_readfirst`` is single read-write port
    * ``bram_1rw_1ro_readfirst`` is one read-write, one read-only port
	* ``bram_1wo_1ro_readfirst`` is one write-only, one read-only port (useful for storing private keys)
	
* **modular** contains multiprecision modular adder and subtractor

* **multiword** contains multiprecision integer comparator and mover/copier

* **util** has the following:
    * ``cryptech_clog2.vh`` replacement for Xilinx' notorious clog2()

