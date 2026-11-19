# Group Progress Status

**Class:** D9A  
**Group ID:** D9A_Group15  
**Project title:** Game Score Categorizer (Moore FSM, modification H4 - Category Counters)  
**Group leader:** Jasneevsingh Kalra

## 1. Current milestone status
Use: `Not Started`, `In Progress`, `Completed` or `Blocked`.

| No. | Milestone | Status | Evidence path/link | Last updated |
|---:|---|---|---|---|
| 1 | Problem requirements and assumptions documented | Not Started | [ ] | [ ] |
| 2 | Architecture and block diagram prepared | Not Started | [ ] | [ ] |
| 3 | FSM diagram/table completed, if applicable | Not Started | [ ] | [ ] |
| 4 | Logisim circuit implemented | In Progress | `02_FSM_Logisim/Game_Score_Categorizer_H4.circ` (circuit built; not yet simulated) | 19/11/2026 13:48 |
| 5 | Logisim simulation verified | Not Started | [ ] | [ ] |
| 6 | Verilog RTL completed | Not Started | [ ] | [ ] |
| 7 | Testbench and simulation completed | Not Started | [ ] | [ ] |
| 8 | FPGA synthesis and implementation completed | Not Started | [ ] | [ ] |
| 9 | Hardware demonstration completed | Not Started | [ ] | [ ] |
| 10 | Results, presentation and report uploaded | Not Started | [ ] | [ ] |
| 11 | Final Pull Request created | Not Started | [ ] | [ ] |

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
