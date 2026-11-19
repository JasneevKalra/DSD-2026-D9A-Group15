# FPGA Implementation Results – Game Score Categorizer (H4)

**Board / device:** Real Digital Boolean Board, xc7s50csga324-1 (Spartan-7)
**Tool:** Vivado 2018.3 (synthesis, implementation and bitstream generation completed)
**Top module:** `top_boolean`  |  **Constraints:** `boolean_board.xdc`

## Resource utilization (implemented design)

Source: `utilization_report.png` (Vivado Utilization, hierarchy view).

| Resource | Used | Available | Utilization |
|---|---:|---:|---:|
| Slice LUTs (all as logic) | 92 | 32,600 | < 1 % |
| Slice Registers (flip-flops) | 118 | 65,200 | < 1 % |
| Slices | 57 | 8,150 | about 1 % |
| Bonded IOB | 23 | 210 | 11 % |
| BUFGCTRL | 1 | 32 | 3 % |
| CARRY4 | 20 | | |
| Block RAM | 0 | | |
| DSP | 0 | | |

The CARRY4 count was read with the Tcl command `llength [get_cells -hier -filter {REF_NAME == CARRY4}]`. The Block RAM and DSP sections of the report are empty (no RAM or DSP is used).

### Utilization by module

| Module | Slice LUTs | Slices |
|---|---:|---:|
| `top_boolean` (total) | 92 | 57 |
| `u_core` (`game_score_categorizer`) | 21 | 8 |
| `u_db0` (`debounce`, START) | 23 | 15 |
| `u_db1` (`debounce_0`, ACK) | 23 | 15 |
| `u_db2` (`debounce_1`, RESET) | 22 | 14 |

The 23 bonded IOBs match the design's ports: `mclk` (1), `sw` (4), `btn` (3), `led` (3), `D0_a` (4), `D0_seg` (8).

## Timing summary (implemented design, 100 MHz clock)

Source: `timing_summary.png` (Vivado Design Timing Summary).

| Check | Worst slack | Total violation | Failing endpoints | Endpoints |
|---|---:|---:|---:|---:|
| Setup (WNS / TNS) | 5.534 ns | 0.000 ns | 0 | 212 |
| Hold (WHS / THS) | 0.173 ns | 0.000 ns | 0 | 212 |
| Pulse width (WPWS / TPWS) | 4.500 ns | 0.000 ns | 0 | 119 |

Vivado reports: **All user specified timing constraints are met.** With a 10 ns clock period and 5.534 ns of setup slack, the design has a comfortable margin at 100 MHz.

## Still to add

- Hardware test results and photos.