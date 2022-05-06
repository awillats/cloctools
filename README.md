# CLOCTools
Hello, this is the overview page fo CLOCTools with links to its various repositories. CLOCTools are a library of tools for closed-loop neuroscience.
CLOC Tools includes algorthms for closed-loop control and tools for realtime implementation.  Additionally, related tools, such as the simulation/modeling tool CLEOsim, are also linked from this page.

<img src="figures/Copy of CLOCtools overview.png" height=180 style='border:15px solid #ffffff'></img>


## Core Algorithms

### **State-space dynamics** (GLDS, PLDS) [`stanley-rozell/ldsCtrlEst`](https://github.com/stanley-rozell/lds-ctrl-est)

<img src="/figures/lds_ctrl_est_logo2022.png" height=90 style='border:15px solid #ffffff'></img>

ldsCtrlEst is a C++ library for estimation and control of linear dynamical systems (LDS) with Gaussian or Poisson observations. It is meant to provide the functionality necessary to implement feedback control of linear dynamical systems experimentally. This library was originally developed for the task of controlling neuronal activity using spike count data as feedback and optogenetic inputs for control.
  - [code](https://github.com/stanley-rozell/lds-ctrl-est), [documentation](https://stanley-rozell.github.io/lds-ctrl-est/)
  - features:
    - estimation & feedback control 
      - parameter adaptive estimation
    - switched estimation & control 
    - Gaussian & Poisson observation models 
    
  <details><summary>examples scripts:</summary>
    
  - GLDS control - [`eg_glds_ctrl.cpp`](https://stanley-rozell.github.io/lds-ctrl-est/docs/api/examples/eg_glds_ctrl_8cpp-example/#example-eg_glds_ctrl.cpp) - [tutorial](https://stanley-rozell.github.io/lds-ctrl-est/docs/tutorials/eg_glds_control/)
  - GLDS control of PLDS - [`eg_glds_du_plds_ctrl.cpp`](https://stanley-rozell.github.io/lds-ctrl-est/docs/api/examples/eg_glds_du_plds_ctrl_8cpp-example/#example-eg_glds_du_plds_ctrl.cpp)
    - change in control (du) is being updated, rather than amplitude (u).
  - PLDS control - [`eg_plds_ctrl.cpp`](https://stanley-rozell.github.io/lds-ctrl-est/docs/api/examples/eg_plds_ctrl_8cpp-example/#example-eg_plds_ctrl.cpp)
  - PLDS estimation - [`eg_plds_est.cpp`](https://stanley-rozell.github.io/lds-ctrl-est/docs/api/examples/eg_plds_est_8cpp-example/#example-eg_plds_est.cpp) - [tutorial](https://stanley-rozell.github.io/lds-ctrl-est/docs/tutorials/eg_plds_state_estimation/)
  - Switched PLDS control [`eg_plds_switched_ctrl.cpp`](https://stanley-rozell.github.io/lds-ctrl-est/docs/api/examples/eg_plds_switched_ctrl_8cpp-example/#example-eg_plds_switched_ctrl.cpp) - [tutorial](https://stanley-rozell.github.io/lds-ctrl-est/docs/tutorials/eg_switched_plds_control/)
</details>

<details><summary>RTXI modules:</summary>

  - [rtxi-gldsController](https://github.com/stanley-rozell/rtxi-gldsController)
  - [rtxi-pldsSimulator](https://github.com/stanley-rozell/rtxi-pldsSimulator)
  - [rtxi-pldsSwitchedController](https://github.com/stanley-rozell/rtxi-pldsSwitchedController)
</details>
<!-- - ( 🚧python example by kjohnsen) -->


### **Latent-switch decoding** (HMM) [`stanley-rozell/hmm`](https://github.com/stanley-rozell/hmm)

<img src="/figures/hmmlogo_center_white.png" height=150></img>

hmm is a simple set of hidden Markov model (HMM) code intended to support control of switching linear dynamical systems.

It contains methods for generating and decoding systems with discrete latent states and discrete observed signals.
  - [code](https://github.com/stanley-rozell/hmm), [documentation](https://stanley-rozell.github.io/hmm/)
  - features
    - Hidden Markov Model (HMM) simulation
    - HMM decoding
  - example script:
    - build, simulate and decode - [`test/main.cpp`](https://github.com/stanley-rozell/hmm/blob/master/misc/test-cmake-installation/src/main.cpp) - [tutorial](https://stanley-rozell.github.io/hmm/_tutorial.html)
  - RTXI modules:
    - [rtxi-hmmDecoder](https://github.com/stanley-rozell/rtxi-hmmDecoder)
    - [rtxi-hmmGenerator](https://github.com/stanley-rozell/rtxi-hmmGenerator)


<!-- ### Local field potential (LFP) decoding
https://github.com/stanley-rozell/lfp-cpp-library
https://github.com/stanley-rozell/lfp-cpp-library/blob/master/src/lfpRatiometer.cpp -->

## Implementation tools


### Cross-language utilities

- [eg-cpp-library](https://github.com/stanley-rozell/eg-cpp-library) - An example repository for C++ library development
- [lds-ctrl-est-pybind]() - python bindings to lds-ctrl-est core C++ functionality
- `cpp-matlab-demos` - using mex to verify algos in c++ *(no repo yet)*

### Real-time utilities ([RTXI](http://rtxi.org/), [TDT](https://www.tdt.com/) )
## RTXI
RTXI, the Real-Time eXperiment Interface, is a hard real-time data acquisition and control application for biological research. At its core is a Real-Time Operating System (RTOS), which uses a modified Linux kernel to provide deterministic control in a variety of experimental settings. RTXI is a fast, free, and open-source system currently used in labs all over the world to probe diverse, technologically challenging problems, such as dynamic probing of ion-channel function, control of cardiac arrhythmia dynamics, and control of deep-brain stimulation patterns.  We have repositories with useful tools for interfacing with and configuring RTXI>

- [rtxi-settings](https://github.com/stanley-rozell/rtxi-settings) -  RTXI experiment settings   
- [stimLoader](https://github.com/stanley-rozell/rtxi-stimLoader) - Stimulus and parameter I/O 
- <details><summary>RTXI signal processing modules  </summary>  

    - https://github.com/old-rtxi-utilities
    - [quanitzer](https://github.com/old-rtxi-utilities/rtxi-quantizer)
    - [gain modulation](https://github.com/old-rtxi-utilities/rtxi-gain_mod)
    - [limiter](https://github.com/old-rtxi-utilities/rtxi-limiter)
    - [nonlinearity & spiking](https://github.com/old-rtxi-utilities/rtxi-nonlin_spike)
  </details>

## TDT  
 Tucker Davis Technologies have a variety of hardware and software solutions of neuroscience.  We have respositories with useful tools for interfacing with TDT hardware and software. 
- <details><summary>TDT utilities</summary>

  - [rtxi-tdtSpikes](https://github.com/stanley-rozell/rtxi-tdtSpikes) - retrieve spike counts from TDT
  - [rtxi-tdtLFP](https://github.com/stanley-rozell/rtxi-tdtLFP) - receive local field potential (LFP)
  - [tdtUDP](https://github.com/stanley-rozell/tdtUDP) - A repository for receiving/sending data through Tucker Davis Technologies UDP interface
</details>

## Satellite repositories 
These projects contain related work from the Rozell lab.
### StAC
[StAC](https://github.com/awillats/state-aware-control) - State-aware control of switching neural dynamics (StAC) applies control, decoding, and estimation to switching models of neural responses. Hidden Markov models and Poisson linear dynamical systems are used to design and characterize feedback in simulation and are compared to non-switching “state-naive” approaches.
### CLEOsim
[CLEOsim](https://github.com/kjohnsen/cleosim) - Closed Loop, Electrophysiology, and Optogenetics Simulator

<img src="/figures/CLEOsim_logo.png" height=90 style='border:15px solid #ffffff'></img>

CLEOsim (Closed Loop, Electrophysiology, and Optogenetics Simulator) is a Python package built on the Brian 2 spiking neural network simulator developed bridging theory and experiment for mesoscale neuroscience, facilitating electrode recording, optogenetic stimulation, and closed-loop experiments.  In conjunction with algorithm toolsets such as lds-ctrl-est and HMM, CLEOSim can test contol algorithms for use in closed-loop neuroscience on Brian 2 spiking neural network models.  In conjunction with implementation toolsets such as lds-ctrl-est-pybind, CLEOSim can also serve to prototype closed-loop experiments in silico.

<img src="/figures/CLOCTools_Overview.png" height=180 style='border:15px solid #ffffff'></img>

### CLINIC
[CLINC](https://github.com/awillats/clinc) - Closed-loop identifiability in neural circuits. This project proposes a framework for understanding the impact of open and closed-loop interventions in identifying neural circuits. This manuscript (in preparation) summarizes the role of stimulation in circuit inference and demonstrates how to design interventions through simple gaussian network simulations. See also [https://github.com/awillats/brian_delayed_gaussian](awillats/brian_delayed_gaussian) for simulating networks of Gaussian nodes with delayed connections in the Brian2 simulator framework.
