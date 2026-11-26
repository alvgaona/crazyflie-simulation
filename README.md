# crazyflie_simulation

## Standalone CrazySim usage

This repo is used on its own, next to a SITL build of [crazyflie-firmware](https://github.com/alvgaona/crazyflie-firmware) (no submodules).

```bash
pixi install                                   # mujoco, numpy, drone-models
export CF2_BUILD_DIR=<crazyflie-firmware>/sitl_make/build
pixi run bash simulator_files/mujoco/launch/sitl_singleagent.sh -m cf2x_T350 -x 0 -y 0
# connect cflib (>= 0.1.34) to udp://127.0.0.1:19850
```

Simulator link: CRTP port `0x0B` (`CRTP_PORT_SIM` in `simulator_files/mujoco/crazysim.py`, `CRTP_PORT_SETPOINT_SIM` in the
firmware's `crtp.h` and the Gazebo plugin's `CrtpUtils.h`); all three must match. On macOS the viewer runs under `mjpython`.
The Gazebo plugin is built from `simulator_files/gazebo/plugins/CrazySim` into `build/crazysim_gz` (override with `CRAZYSIM_GZ_BUILD_DIR`).


Hi! Welkom to the crazyflie simulation repo. This repo is still at the early stages and still in development so just ask if you are looking for anything in particular.

Currently it contains low resolution meshes based on the design of the actual [crazyflie 2.1](https://www.bitcraze.io/products/crazyflie-2-1/) but heavily simplified to contain as little vertices as possible, so it can be used to simulate a lot of them.


## Installation

See the  [installation instructions](/docs/installing/) in the Github docs folder.

## Official documentation

Check out the [Bitcraze crazyflie-simulation documentation](https://www.bitcraze.io/documentation/repository/crazyflie-simulation/main/) on our website.

## Contribute

Go to the [contribute page](https://www.bitcraze.io/development/contribute/) on our website to learn more.
