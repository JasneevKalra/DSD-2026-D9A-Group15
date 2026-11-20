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

## Hardware demonstration

The bitstream was programmed on the Real Digital Boolean Board on 20/11/2026 (the board's DONE LED is lit in the photos). The group reports that the hardware demonstration was completed and recorded on video.

**Photographed case: score 5 (MEDIUM), after a reset**

| Item | Expected | Observed in the photo |
|---|---|---|
| LED | MEDIUM LED (LD1) on | LD1 lit |
| 7-segment display 0 | state 2 (MEDIUM), LOW count 0, MEDIUM count 1, HIGH count 0 | reads 2 0 1 0 |

The display digits are, left to right: state (0 IDLE, 1 LOW, 2 MEDIUM, 3 HIGH), LOW count, MEDIUM count, HIGH count. The score itself is shown only by the switches.

Evidence: `hardware_photo_board_score5_medium.jpg` (whole board) and `hardware_photo_display_score5_closeup.jpg` (display close-up).

## Still to add

- The demonstration video (or a link to it) and the observations for the other test cases.