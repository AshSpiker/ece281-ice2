# ICE 2: Half-Adder

Code for [ECE 281 ICE 2: Half-Adder](https://usafa-ece.github.io/ece281-book/ICE/ICE2.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Windows 11 using Vivado 2024.

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/hdl/`.

Then it **elaborates** the *any* entity with the name `*_tb`. In this case, that is `helloled_tb`.

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail **with** `severity failure` then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.


Documentation Statement:
For this assignment I used the provided resources and no unauthorized resources. I recieved help with Dr. York during class when my Vivado was having issues, other than that I received no help. 
I completed the demo outside of class and took a video of the working project. The link is (https://teams.microsoft.com/l/message/48:notes/1737605981696?context=%7B%22contextType%22%3A%22chat%22%7D)
I recieved no other help and used no unauthorized resources.