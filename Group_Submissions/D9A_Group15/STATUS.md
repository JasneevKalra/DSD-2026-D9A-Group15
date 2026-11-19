# Group Progress Status

**Class:** D9A  
**Group ID:** D9A_Group15  
**Project title:** Game Score Categorizer (Moore FSM, modification H4 - Category Counters)  
**Group leader:** Jasneevsingh Kalra

## 1. Current milestone status
Use: `Not Started`, `In Progress`, `Completed` or `Blocked`.

| No. | Milestone | Status | Evidence path/link | Last updated |
|---:|---|---|---|---|
| 1 | Problem requirements and assumptions documented | Completed | `01_Problem_Analysis/problem_analysis.md` | 19/11/2026 |
| 2 | Architecture and block diagram prepared | Not Started | [ ] | [ ] |
| 3 | FSM diagram/table completed, if applicable | Completed | `02_FSM_Logisim/fsm_state_diagram.webp`, `02_FSM_Logisim/fsm_state_table.md` | 19/11/2026 |
| 4 | Logisim circuit implemented | Completed | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ` | 19/11/2026 |
| 5 | Logisim simulation verified | Completed | `02_FSM_Logisim/simulation/simulation_results.md` and `sim_01` to `sim_15` screenshots (all 14 planned tests passed) | 19/11/2026 |
| 6 | Verilog RTL completed | Completed | `03_Verilog_Implementation/RTL/game_score_categorizer.v` (compiled in Vivado without errors, as reported by the group) | 19/11/2026 15:45 |
| 7 | Testbench and simulation completed | Completed | `03_Verilog_Implementation/Simulation_Results/simulation_results.md` (Vivado XSim: 88 checks, 0 errors, TEST PASSED; waveforms for Test 1) | 19/11/2026 |
| 8 | FPGA synthesis and implementation completed | Completed | `04_FPGA_Hardware/boolean_board.xdc`, `04_FPGA_Hardware/fpga_results.md`, `04_FPGA_Hardware/utilization_report.png` (92 LUTs, 118 flip-flops, 20 CARRY4; timing report still to add) | 19/11/2026 |
| 9 | Hardware demonstration completed | Not Started | [ ] | [ ] |
| 10 | Results, presentation and report uploaded | Not Started | [ ] | [ ] |
| 11 | Final Pull Request created | In Progress | https://github.com/MrugendraVasmatkar/Digital_System_Design_Practical_2026_27_D9A_B/pull/9 (opened; will be updated as remaining deliverables are added) | 19/11/2026 |

## 2. Time-wise progress log
Update at least once every two hours and at each major milestone. Record actual work and actual times; do not pre-fill future updates.

| Date | Actual time | Work completed | Evidence path | Blocker | Next action | Updated by |
|---|---|---|---|---|---|---|
| 19/11/2026 | 02:07 | Pre-exam setup: repo forked and renamed to DSD-2026-D9A-Group15, origin updated, group folder `D9A_Group15` created from template, team details filled in README | `Group_Submissions/D9A_Group15/README.md` | Problem statement not yet released; teammates' GitHub usernames pending | Get problem statement, start Stage 1 | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 13:48 | Problem statement received (Game Score Categorizer, hint H4 Category Counters). Logisim circuit built: 4-bit score comparators, 2-bit Moore FSM (IDLE/LOW/MEDIUM/HIGH), LED outputs, three 4-bit category counters | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ` | Circuit not yet simulated in Logisim; no test evidence yet | Run test sequence in Logisim, capture screenshots, then draw FSM diagram and state table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 13:56 | Started step-by-step Logisim guidance for hint H2 (Mealy FSM, immediate output, no input register). Gate equations checked exhaustively in a script (512 input/state combinations, 0 mismatches vs. the intended Mealy behaviour). Phase 1 (Logisim basics) given. | scratchpad script `verify_mealy.js` (equations only; no Logisim circuit built or simulated for H2 yet) | Logisim/Java not found on this PC to open a circuit; STATUS title still says H4 while the user asked for H2 - to be confirmed | Phases 2-12: build and test the H2 circuit in Logisim, then draw Mealy diagram and state table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 14:05 | H2 Mealy Logisim file generated (40 gates, 2 D flip-flops, no tunnels, rail layout, LED outputs). Checked with a script that rebuilds the netlist from the .circ text and simulates it (checkpoint 1, tests A/B/C, 20000 random steps: all pass) | `02_FSM_Logisim/Game_Score_Categorizer_H2_Mealy.circ` | File NOT yet opened in real Logisim (not installed here); pin positions of gates/flip-flop are assumed | Open in Logisim, confirm no blue/red wires, run tests, take screenshots | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 14:14 | H2 Mealy Logisim file re-spaced (wider rows/columns/rails, same logic, same 40 gates); re-checked with the same script, all tests pass | `02_FSM_Logisim/Game_Score_Categorizer_H2_Mealy.circ` | Still not opened in real Logisim | Open in Logisim, confirm no blue/red wires, run tests, screenshots | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 14:30 | Decision: final design uses hint H4 (Category Counters). The H2 Mealy circuit rows above are discarded; the H2 file was never uploaded to the repo. Repo folder structure checked against template (Verilog `RTL/`, `Testbench/`, `Simulation_Results/` subfolders added); teammates' GitHub usernames added to README | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ`, `03_Verilog_Implementation/` | H4 circuit still not simulated in Logisim; problem analysis, FSM diagram/table, results, presentation and report still missing | Simulate H4 in Logisim with screenshots; write problem analysis and FSM diagram/table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 15:44 | Stage 2: Verilog RTL (core FSM + counters, debouncer, Boolean Board top with 7-segment display), self-checking testbench (all 16 scores, hold/count-once, idle, 4-bit wrap, async reset) and Boolean Board XDC written and uploaded | `03_Verilog_Implementation/RTL/game_score_categorizer.v`, `03_Verilog_Implementation/Testbench/tb_game_score_categorizer.v`, `04_FPGA_Hardware/boolean_board.xdc` | Not yet compiled or simulated in Vivado; XDC pins taken from Real Digital tutorial, segment/digit order unverified on the board | Run behavioral simulation in Vivado and save waveform/log to `Simulation_Results/`; synthesize and program the board | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 15:45 | Vivado: Verilog compiled and synthesis, implementation and bitstream generation completed successfully (reported by the group) | `03_Verilog_Implementation/RTL/game_score_categorizer.v`, `04_FPGA_Hardware/boolean_board.xdc` | Behavioral simulation result not yet recorded; utilization/timing reports and screenshots not yet uploaded; hardware not yet tested | Run/save simulation waveform and log; upload utilization and timing report screenshots; program the Boolean Board and test | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 15:50 | Problem analysis written: summary, objectives, I/O table, requirements, assumptions, constraints, edge cases, proposed solution and feasibility | `01_Problem_Analysis/problem_analysis.md` | FPGA utilization figures to be added from the Vivado report | Draw FSM diagram, write state table, add Logisim simulation evidence | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 15:59 | Moore FSM state diagram checked against the Logisim/Verilog design (correct) and uploaded. The first state-table image had errors (ignored the score category in IDLE; showed ACK=1 in IDLE returning to IDLE; START=1 in a category state ignored ACK), so it was replaced by a corrected table with encoding, outputs, counter actions and Boolean equations | `02_FSM_Logisim/fsm_state_diagram.webp`, `02_FSM_Logisim/fsm_state_table.md` | Logisim simulation screenshots and filled test table still missing | Run H4 circuit in Logisim, capture screenshots, fill expected-vs-observed table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 16:12 | Pull request opened to the faculty master repository (base main, head JasneevKalra:main); only Group_Submissions/D9A_Group15 changed | PR #9: https://github.com/MrugendraVasmatkar/Digital_System_Design_Practical_2026_27_D9A_B/pull/9 | Logisim/Vivado simulation evidence, utilization and timing reports, hardware demo, results, presentation and report still pending | Keep pushing to the fork; the PR updates automatically | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:07 | Logisim circuit opened and exported as a full-circuit image (inputs, range decoder, state registers, next-state/output logic, three 4-bit counters, LEDs, count outputs) | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ`, `02_FSM_Logisim/logisim_circuit_full.webp` | Simulation screenshots (states, counters, reset) and filled test table still missing | Run the test sequence in Logisim, capture screenshots, fill expected-vs-observed table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:29 | Full-circuit image (logisim_circuit_full.webp) removed from the repo at the group's request; it was a printer-view export without live values and is not simulation evidence | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ` | Real simulation screenshots (with pin values) still missing | Capture screenshots in simulation mode and upload them | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:33 | Logisim simulation screenshots added for 3 tests: reset/IDLE, LOW (score 3) and HIGH (score 12); all matched the expected LED and counter values. Three printer-view exports without live values were not used | `02_FSM_Logisim/simulation/` | MEDIUM, ACK, boundary scores, hold, count-once and counter-repeat screenshots still missing | Capture the remaining tests in simulation mode | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:44 | Logisim simulation screenshots and simulation_results.md removed from the repo at the group's request; the group will upload the complete set together | none | Simulation evidence not in the repo | Upload all Logisim simulation screenshots together and record results | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:49 | Logisim simulation screenshots uploaded together: reset/IDLE, LOW (3), MEDIUM (7), HIGH (12) and ACK return to IDLE. All matched expected states, LEDs and counter values; counters rose 1/0/0, 1/1/0, 1/1/1 | `02_FSM_Logisim/simulation/` | Boundary scores, hold, count-once, repeated detections and reset-clears-non-zero-counters screenshots still missing | Capture the remaining tests and complete the table | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:54 | Logisim hold test added: in HIGH state, changing Score to 1 with START=1 left the state at HIGH and the counts unchanged (0/0/1), as expected | `02_FSM_Logisim/simulation/sim_06_hold_state.png` | Boundary scores, count-once, repeated detections and reset-clears-non-zero-counters screenshots still missing | Capture the remaining tests | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 18:57 | Logisim boundary tests added: score 4 gives LOW, 5 gives MEDIUM, 9 gives MEDIUM, 11 gives HIGH; each incremented only its own counter. The screenshot meant for score 10 shows 1001 (9) | `02_FSM_Logisim/simulation/sim_07` to `sim_10` | Score 10 boundary, count-once, repeated detections and reset-clears-non-zero-counters screenshots still missing | Capture score 10 (1010) and the remaining tests | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 19:01 | Group decided to skip the score-10 test (9 and 11 were tested on either side of it); recorded in simulation_results.md | `02_FSM_Logisim/simulation/simulation_results.md` | Count-once, repeated detections and reset-clears-non-zero-counters screenshots still missing | Capture the remaining three tests | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 19:03 | Logisim score-10 test captured after all: Score 1010 gives MEDIUM, MEDIUM_COUNT rose to 3 with the other counts unchanged. All boundary scores 4, 5, 10 and 11 now tested | `02_FSM_Logisim/simulation/sim_11_score10_medium.png` | Count-once, repeated detections and reset-clears-non-zero-counters screenshots still missing | Capture the remaining three tests | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 19:18 | Logisim simulation completed: count-once (START held, count stays 1), repeated LOW detections (counts 1, 2, 3) and reset clearing non-zero counters (3 to 0) captured. All 14 planned tests passed; one duplicate screenshot was dropped | `02_FSM_Logisim/simulation/` | Verilog/Vivado simulation evidence, utilization and timing reports, hardware test, results, presentation and report still missing | Run Vivado simulation and save waveform and log; upload reports; test on the Boolean Board | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 19:35 | Vivado behavioral simulation run to completion: Checks run 88, Errors 0, TEST PASSED, $finish at 1760 ns. Console and waveform screenshots uploaded | `03_Verilog_Implementation/Simulation_Results/` | Utilization and timing reports, hardware test, results, presentation and report still missing | Upload utilization and timing report screenshots; test on the Boolean Board | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 19:41 | Vivado utilization report uploaded: 92 Slice LUTs, 118 flip-flops, 57 slices, 23 bonded IOBs, 1 BUFGCTRL, no Block RAM or DSP | `04_FPGA_Hardware/utilization_report.png`, `04_FPGA_Hardware/fpga_results.md` | CARRY4 count and timing summary not yet uploaded; hardware not yet tested | Upload CARRY4 count and timing summary; test on the Boolean Board | Claude (for Jasneevsingh Kalra) |
| 19/11/2026 | 20:11 | CARRY4 count added to the FPGA results: 20 (read from the implemented design with a Tcl command) | `04_FPGA_Hardware/fpga_results.md` | Timing summary (WNS, WHS) and hardware test still missing | Upload timing summary; test on the Boolean Board | Claude (for Jasneevsingh Kalra) |
| 20/10/2026 | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

Add rows as needed.

## 3. Current blockers and support required
| Blocker | Impact | Action being taken | Faculty support required |
|---|---|---|---|
| [ ] | [ ] | [ ] | [ ] |

## 4. End-of-day summary
### 19 October 2026
- Completed:
- In progress:
- Pending:
- Evidence uploaded:
- Plan for 20 October:

### 20 October 2026
- Completed:
- Pending:
- Evidence uploaded:
- Final submission status:

## 5. Group leader confirmation
I confirm that this status reflects the work completed by the group and that the linked evidence has been uploaded.

**Group leader:** Jasneevsingh Kalra  
**Date/time:** [Actual date and time]
