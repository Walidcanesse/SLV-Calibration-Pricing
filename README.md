# Stochastic Local Volatility — Calibration & Exotic Pricing

Calibration of a Stochastic Local Volatility (SLV) model via the **particle method** (McKean-Vlasov SDE), and pricing of a **forward-starting call spread**.

## Overview

The SLV model combines stochastic volatility with a leverage function to produce trajectories with realistic vol dynamics while calibrating exactly to vanilla option prices. This project implements:

- **Particle method** for calibrating the leverage function $l(t, S)$ via kernel regression (Nadaraya-Watson estimator with quartic kernel)
- **Validation** that the calibrated model reproduces the market smile
- **Sensitivity analysis** of $\gamma$ (vol-of-vol), $\rho$ (spot-vol correlation), $\kappa$ (mean-reversion)
- **Pricing** of a forward-starting call spread: BS vs calibrated SLV
- **Visualization** of joint distributions $(S_{T_1}, S_{T_2})$ showing that vanillas constrain marginals but not the joint law

## Key Results

- The particle method calibrates the SLV model to a flat 15% smile with high accuracy
- The forward-starting call spread is priced ~5% higher in SLV than in Black-Scholes — a statistically significant difference driven by vol heterogeneity across paths
- Different parameter choices produce identical vanilla prices but different exotic prices, illustrating the fundamental limitation of vanilla-only calibration

## Tech Stack

Python · NumPy · SciPy · Matplotlib · Plotly

## Context

M2MO Modélisation Aléatoire — Université Paris Cité (2025–2026)  
Course: Advanced Calibration Methods and VIX Derivatives
