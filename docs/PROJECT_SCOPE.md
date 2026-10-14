# What was implemented vs. proposed

This file records the **historical scope** of the May 2025 AquaFlush academic prototype.

| Capability | Evidence / status |
|---|---|
| Arduino Uno flow-pulse reading | Present in recovered sketch |
| Estimated water flow in L/hour | Present in recovered sketch |
| I²C LCD flow display | Present in recovered sketch |
| Serial Monitor flow output | Present in recovered sketch |
| Physical scale drainage model | Shown in May 2025 presentation |
| Water pump and relay in hardware exhibit | Listed/shown in presentation |
| Firmware-controlled pump activation | **Not present** in the sole sketch the group used |
| Autonomous clog detection and threshold alarms | **Not present** in the sole sketch |
| Internet connectivity / cloud data pipeline | Conceptual diagram; no implementation in recovered firmware |
| Validated detection accuracy, quantitative results | Not supplied in presentation |

## Recovered source provenance

The group reported that the approximately 63-line code shown on slide 8 of the presentation was the only firmware used. The original source file was lost. The copy in the repository was reconstructed from that screenshot, so its exact formatting and some details cannot be independently authenticated.

## Project presentation and future iterations

The project presentation uses the broader conceptual title **“Project AquaFlush: IoT-Based Smart Water Clogging Detection and Automation System for Small Urban Drainage Management.”** The README uses a narrower title matching the implemented monitoring feature set.

The presentation recommends improving fluid dynamics, adding sensing technologies, and considering other root causes of clogging. Those are **recommendations for future work**, not software or test results from 2025.
