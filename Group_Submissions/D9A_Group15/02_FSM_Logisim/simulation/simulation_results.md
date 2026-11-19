# Logisim Simulation Results – Game Score Categorizer (H4)

Circuit: `../Game_Score_Categorizer_H4.circ`. Screenshots were taken in Logisim simulation mode with the Poke tool; live pin values, LEDs and counts are visible in each image. State registers `STATE_Q1`/`STATE_Q0` give the state code (IDLE 00, LOW 01, MEDIUM 10, HIGH 11).

## Tests completed

| Test | Inputs | Expected | Observed | Result | Evidence |
|---|---|---|---|---|---|
| T1 Reset / IDLE | `RESET`=1 | State IDLE (00), all LEDs off, all counts 0 | Q1/Q0 = 0/0, all LEDs off, `LOW_COUNT`=`MEDIUM_COUNT`=`HIGH_COUNT`=0000 | Pass | `sim_01_reset_idle.png` |
| T2 LOW category | `Score`=0011 (3), `START`=1 | State LOW (01), `LOW_LED` on, `LOW_COUNT`=1 | Q1/Q0 = 0/1, `LOW_LED` lit (green), `LOW_COUNT`=0001, `MEDIUM_COUNT`=0000, `HIGH_COUNT`=0000 | Pass | `sim_02_low_score3.png` |
| T3 MEDIUM category | `Score`=0111 (7), `START`=1 | State MEDIUM (10), `MEDIUM_LED` on, `MEDIUM_COUNT` +1 | Q1/Q0 = 1/0, `MEDIUM_LED` lit (yellow), `LOW_COUNT`=0001, `MEDIUM_COUNT`=0001, `HIGH_COUNT`=0000 | Pass | `sim_03_medium_score7.png` |
| T4 HIGH category | `Score`=1100 (12), `START`=1 | State HIGH (11), `HIGH_LED` on, `HIGH_COUNT` +1 | Q1/Q0 = 1/1, `HIGH_LED` lit (red), counts LOW/MEDIUM/HIGH = 0001/0001/0001 | Pass | `sim_04_high_score12.png` |
| T5 ACK returns to IDLE | `ACK`=1 after a category detection (`START` still 1, `Score`=1100) | State IDLE (00), LEDs off, counts unchanged | Q1/Q0 = 0/0, all LEDs off, counts still 0001/0001/0001 | Pass | `sim_05_ack_return_idle.png` |
| T6 State holds | In HIGH after a score-12 detection, no ACK; then Score changed to 0001 (1) with START=1 | State stays HIGH, no counter changes, even though score 1 would be LOW | Q1/Q0 = 1/1, HIGH_LED still lit (red), counts LOW/MEDIUM/HIGH = 0000/0000/0001; GO = 0 | Pass | `sim_06_hold_state.png` |

The counts rise 1/0/0, 1/1/0, 1/1/1 across T2, T3 and T4, showing each detection increments only its own category counter.

## Tests still to capture

- Boundary scores 4, 5, 10 and 11.
- `START` held for several ticks counting only once.
- Counters after repeated detections of the same category.
- `RESET` clearing counters that were non-zero (the reset screenshot shows counts already at 0000).
