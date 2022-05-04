# CLOCTools
Hello, this is the overview page fo CLOCTools and its various repositories. CLOCTools are a library of tools for closed-loop neuroscience.
CLOC Tools includes algorthms for closed-loop control and tools for realtime implementation.  Additionally, related closed-loop tools, such as the simulation/modeling tools CLEOsim, are also linked from this page.


## Core Algorithms
<img src="/figures/ldsctrlest-logo.png" height=45 style='border:15px solid #ffffff'></img><img src="/figures/hmmlogo_center_white.png" height=75></img>
### **State-space dynamics** (GLDS, PLDS) [`stanley-rozell/ldsCtrlEst`](https://github.com/stanley-rozell/lds-ctrl-est)
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
- [rtxi-settings](https://github.com/stanley-rozell/rtxi-settings) -  RTXI experiment settings   
- [stimLoader](https://github.com/stanley-rozell/rtxi-stimLoader) - Stimulus and parameter I/O 
- <details><summary>RTXI signal processing modules  </summary>  

    - https://github.com/old-rtxi-utilities
    - [quanitzer](https://github.com/old-rtxi-utilities/rtxi-quantizer)
    - [gain modulation](https://github.com/old-rtxi-utilities/rtxi-gain_mod)
    - [limiter](https://github.com/old-rtxi-utilities/rtxi-limiter)
    - [nonlinearity & spiking](https://github.com/old-rtxi-utilities/rtxi-nonlin_spike)
  </details>
  
- <details><summary>TDT utilities</summary>

  - [rtxi-tdtSpikes](https://github.com/stanley-rozell/rtxi-tdtSpikes) - retrieve spike counts from TDT
  - [rtxi-tdtLFP](https://github.com/stanley-rozell/rtxi-tdtLFP) - receive local field potential (LFP)
  - [tdtUDP](https://github.com/stanley-rozell/tdtUDP) - A repository for receiving/sending data through Tucker Davis Technologies UDP interface
</details>

## Satellite repositories 
These projects contain related work from the Rozell lab
- [StAC](https://github.com/awillats/state-aware-control) - state-aware control of switching neural dynamics
- [CLEOsim](https://github.com/kjohnsen/cleosim) - Closed Loop, Electrophysiology, and Optogenetics Simulator
  - <img src="/figures/CLEOsim_logo.png" height=45 style='border:15px solid #ffffff'></img> 
- [CLINC](https://github.com/awillats/clinc) - closed loop identifiability in neural circuits
