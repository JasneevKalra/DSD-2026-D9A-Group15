# Logisim Simulation Results – Game Score Categorizer (H4)

Circuit: `../Game_Score_Categorizer_H4.circ`. Screenshots were taken in Logisim simulation mode with the Poke tool; live pin values, LEDs and counts are visible in each image.

## Tests completed

| Test | Inputs | Expected | Observed | Result | Evidence |
|---|---|---|---|---|---|
| T1 Reset / IDLE | `RESET`=1 (Score shows 1100) | State IDLE (00), all LEDs off, all counts 0 | State registers 0/0, LOW/MEDIUM/HIGH LEDs off, `LOW_COUNT`=`MEDIUM_COUNT`=`HIGH_COUNT`=0000 | Pass | `sim_01_reset_idle.png` |
| T2 LOW category | `Score`=0011 (3), `START`=1 | State LOW (01), `LOW_LED` on, `LOW_COUNT`=1 | State registers 0/1, `LOW_LED` lit (green), `LOW_COUNT`=0001, `MEDIUM_COUNT`=0000, `HIGH_COUNT`=0000 | Pass | `sim_02_low_score3.webp` |
| T3 HIGH category | `Score`=1100 (12), `START`=1 | State HIGH (11), `HIGH_LED` on, `HIGH_COUNT` +1 | State registers 1/1, `HIGH_LED` lit (red), `HIGH_COUNT`=0001; `LOW_COUNT`=0001 and `MEDIUM_COUNT`=0010 from earlier detections in the same run | Pass | `sim_03_high_score12.png` |

## Tests still to capture

- MEDIUM category (score 7) and the yellow LED.
- ACK returning the machine to IDLE.
- Boundary scores 4, 5, 10 and 11.
- State holding while the score changes and `START` is pressed again.
- `START` held for several ticks counting only once.
- Counters after repeated detections.
- RESET clearing non-zero counters.
