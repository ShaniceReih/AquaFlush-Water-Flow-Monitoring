# AquaFlush hardware and wiring notes

These connections are inferred **from the recovered firmware and standard Arduino Uno I²C pins**. Confirm against the physical 2025 prototype before connecting hardware.

| Connection | Arduino Uno |
|---|---|
| Water-flow sensor pulse signal | D2 (external interrupt 0) |
| LCD SDA | A4 (I²C data) |
| LCD SCL | A5 (I²C clock) |
| Sensor and LCD power | Match each module's rated supply; share ground where required |

The recovered code assumes the I²C LCD address is `0x27`. Its actual I²C address may differ.

## Other parts visible or listed in the 2025 presentation

The presentation also identifies a **5 V relay** and **water pump** in the scale drainage exhibit. The recovered firmware contains **no relay output, relay pin definition, pump timing, or motor driver code**. Therefore, no pump-control wiring map can be responsibly reconstructed from the firmware.

## Flow sensing

- The code attaches `flow()` as a rising-edge external-interrupt handler on interrupt 0 / digital pin 2.
- Every approximately 1000 ms, it converts the accumulated pulses into an estimated value in liters per hour.
- The divisor `7.5` is an assumed calibration factor, not a documented measurement for this exact sensor.
- The interrupt counter is read/reset without an atomic section. This may cause occasional small measurement error; preserving the recovered code does not mean that edge case is resolved.

## Electrical safety

Use a properly rated supply for any pump, never an Arduino GPIO pin. Confirm module voltage ratings, isolation, protective components, and water-resistant enclosure requirements prior to physical reuse.
