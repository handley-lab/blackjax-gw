# blackjax-gw

Gravitational wave parameter estimation using BlackJAX nested sampling and Jim gravitational wave analysis tools.

## Core Dependencies

This project requires two main repositories:

1. **BlackJAX** (nested sampling branch): `git+https://github.com/handley-lab/blackjax@nested_sampling`
   - Provides Bayesian nested sampling algorithms
   - Used for parameter estimation and evidence calculation

2. **Jim**: `git+https://github.com/kazewong/jim` 
   - Gravitational wave analysis framework
   - Provides detectors (H1, L1), likelihood functions, waveforms, priors, and transforms

## Installation

```bash
pip install uv
uv pip install "jax[cuda12_pip]"==0.4.31 -f https://storage.googleapis.com/jax-releases/jax_cuda_releases.html git+https://github.com/handley-lab/blackjax@nested_sampling git+https://git.ligo.org/lscsoft/ligo-segments.git git+https://github.com/kazewong/jim anesthetic
```

## Usage

The main analysis script is `ICML/run_GW150419.py`, which performs parameter estimation on gravitational wave data using:
- RippleIMRPhenomD waveform model
- HeterodynedTransientLikelihoodFD likelihood
- 11-parameter prior (masses, spins, sky position, etc.)
- Custom periodic boundary handling for angular parameters

## Jim Version Notes
- OLD VERSION: 03842792626c3a14ec8885f8076833324c391db2 (current codebase)
- NEW VERSION: 3d0116844d921ea7a035973137386d5bbb71c0d4 (updated)
- Ming's version: https://github.com/ming-256/jim/commits/main/

Jim provides:
- LIGO detector data loading
- Various likelihood implementations (phase marginalisation, heterodyning)
- Detector models for signal injection

