
# Thrust Control of a Lunar Lander

## Introduction

This project investigates the performance of propulsion systems for a lunar lander through detailed simulations conducted in MATLAB Simulink. The focus is on how variations in mass flow rate and exhaust velocity impact thrust generation. The primary goal is to develop accurate and dynamic models that reflect the operational characteristics of the propulsion systems.

The project is structured around two main objectives:
1. **Ideal Case Simulation**: Simulate the propulsion system under ideal conditions to establish a theoretical benchmark for thrust production, providing an understanding of the system’s maximum potential thrust.
2. **Non-Ideal Case Simulation**: Incorporate real-world complexities like pressure differentials and system losses to create a realistic representation of thrust generation.

System identification is performed using Simulink’s System Identification Toolbox, using data obtained from research papers to refine the models and improve simulation accuracy.

## Theory

### General Thrust Equation
Thrust is the force that propels an object forward and is a crucial parameter in propulsion systems like rockets. The general thrust equation is:
F = ṁve + (Pe − Pa)Ae

Where:
- **F**: Thrust (N)
- **ṁ**: Mass flow rate (kg/s)
- **ve**: Exhaust velocity (m/s)
- **Pe**: Exhaust pressure (Pa)
- **Pa**: Ambient pressure (Pa)
- **Ae**: Nozzle exit area (m²)

### Ideal Case
In ideal conditions:
- Perfect expansion (Pe = Pa)
- No losses (thermal, frictional, etc.)
- Steady flow
- Isentropic process

The thrust equation simplifies to:
F = ṁve


### Non-Ideal Case
In real-world conditions:
- Imperfect expansion (Pe ≠ Pa)
- Losses occur (friction, thermal, etc.)
- Unsteady flow
- Non-isentropic process

The full thrust equation is used:
F = ṁve + (Pe − Pa)Ae

## Simulation

### Ideal Case
- **Thrust Equation**: `F = ṁve`
- **Exhaust Velocity (ve)**: Determined using `ve = Isp * g`, with specific impulse (Isp ≈ 300s), leading to ve ≈ 2940 m/s.
- **Transfer Function**: First-order, `F(s) = (2940 / (0.5s + 1)) * Ṁ(s)`
- **Input**: Pulse train simulating mass flow rate variations. Total mass flow rate assumed to be 10 kg/s.
- **Duration**: 10 seconds.

### Non-Ideal Case
- **Thrust Equation**: `F = ṁve + (Pe − Pa)Ae`
- **System Identification**: Performed using empirical data to refine the dynamic model, capturing non-ideal behaviors.
- **Transfer Function**: Derived from system identification with higher-order dynamics.
- **Input**: Pulse train similar to the ideal case.
- **Duration**: 10 seconds.

## Conclusion

This project successfully simulated propulsion systems for a lunar lander, establishing both theoretical benchmarks and realistic models. System identification techniques enhanced model accuracy, providing valuable insights for optimizing propulsion system efficiency and performance.

---

### References
- [NASA Thrust Explanation](https://www.grc.nasa.gov/www/k-12/airplane/rockth.html)
- [NASA Thrust Summary](https://www.grc.nasa.gov/www/k-12/airplane/rktthsum.html)
- [NASA Specific Impulse](https://www.grc.nasa.gov/www/k-12/airplane/specimp.html)
- [Spacecraft Propulsion - Wikipedia](https://en.wikipedia.org/wiki/Spacecraft_propulsion)
- [Specific Impulse - Wikipedia](https://en.wikipedia.org/wiki/Specific_impulse)
