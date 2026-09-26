## Brian Seunghyun Lee

Final-year Electrical & Electronic Engineering undergraduate at Yonsei University, Seoul.

I build hardware for machine learning — and, increasingly, for the part of machine learning that
is actually slow: moving data. My capstone started as an accelerator project and ended up as a
memory-system project, which is roughly the arc I want to keep following.

**Current interest:** memory-centric computing — processing near memory, accelerator
microarchitecture, and the gap between what a datapath can compute and what the memory system can
feed it.

The capstone is written up as a paper:
[*A Near-Data Processing Approach to Accelerating Compaction in LSM-tree Key-Value Stores*](https://github.com/h23yonsei/gem5-pnm-lsm-compaction/blob/main/paper/pnm-compaction-paper.pdf)
(with Jaesik Jang).

### Selected work

| Project | What it is | Result |
| --- | --- | --- |
| [gem5-pnm-lsm-compaction](https://github.com/h23yonsei/gem5-pnm-lsm-compaction) | A processing-near-memory unit in the DIMM buffer chip that takes over RocksDB compaction. Modified gem5 (full-system) plus a RocksDB fork, coupled by an MMIO contract. | Write throughput **+45–59%**, core-0 L2 misses **−54 to −64%** over two full-system runs, with three [limitations](https://github.com/h23yonsei/gem5-pnm-lsm-compaction#limitations-of-the-capstone-runs). [Rerun](https://github.com/h23yonsei/gem5-pnm-lsm-compaction#results-with-the-current-code) after addressing them: **+25%** writes and **+35%** reads on a single-core host; a whole second core, as a control, gives +57% on writes, but its caches alone take an [estimated](https://github.com/h23yonsei/gem5-pnm-lsm-compaction#area-and-power-estimate) 10× the unit's area or more |
| [systolic-mlp-accelerator-zynq](https://github.com/h23yonsei/systolic-mlp-accelerator-zynq) | 16×16 output-stationary systolic array for int8 MLP inference on Zynq-7020, with matrix tiling to keep the working set in on-chip memory. | Timing met at **100 MHz**; in simulation the RTL's output matches the NumPy reference on all 16 clips |
| [npu-conv-accelerator-pynq](https://github.com/h23yonsei/npu-conv-accelerator-pynq) | Configurable convolution accelerator in SystemVerilog on PYNQ-Z2 — AXI4-Lite CSRs, BRAM tiling, and a Python golden model to check it against. | RTL, driven through its AXI4-Lite CSRs, matches the golden model; timing met at **50 MHz** in 12% of the LUTs |
| [fpga-cnn-accelerator-labs](https://github.com/h23yonsei/fpga-cnn-accelerator-labs) | Verilog fundamentals through UART, custom AXI IP, Sobel filtering, and an MNIST CNN accelerator on Spartan-7 / Zynq-7000. | All 18 testbenches run from a clone, in Vivado or Icarus Verilog; the CNN core is pipelined to meet timing at **100 MHz** |
| [tinygpt-transformer-from-scratch](https://github.com/h23yonsei/tinygpt-transformer-from-scratch) | A bigram-to-GPT course curriculum in PyTorch, documented stage by stage, with my own TinyGPT trained on a new dataset at the end. | Held-out loss **1.36** at its best epoch, on a contiguous split; one script checks every notebook's losses against the README table |

The last one is deliberate. If you are designing silicon for a workload, you should be able to
write the workload.

Each repository runs its testbenches or result checks in GitHub Actions on every push.

### Tools

Verilog / SystemVerilog · Vivado · gem5 · C / C++ · Python / PyTorch · Zynq-7000, Spartan-7

---

Seoul, Korea · hyunof23@yonsei.ac.kr
