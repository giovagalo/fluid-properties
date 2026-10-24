# Fluid Properties

A free, offline calculator for the thermophysical properties of the most common HVAC&R fluids. It is a single HTML file that runs in any modern browser, with no installation, no server and no internet connection needed.

**▶ Live tool:** https://giovagalo.github.io/fluid-properties/

![Screenshot](screenshot.png)

## Features

### Water & glycols
- Water, ethylene glycol (MEG) and propylene glycol (MPG), 0–60 % by mass
- Density, specific heat and freezing point
- Heat duty calculator, Q = ṁ · cp · (T₂ − T₁), solving for **heat duty, flow rate, T₁ or T₂**
- Flow in m³/h, l/min, l/s, kg/s, kg/h; duty in kW, W, kcal/h
- Properties evaluated at mean temperature, T₁ or T₂

### Moist air
- Dry bulb plus one of wet bulb, relative humidity or humidity ratio
- Pressure entered directly or computed from altitude
- Wet bulb, dew/frost point, RH, humidity ratio, degree of saturation, enthalpy, specific volume, density, vapour pressures, cp
- Interactive psychrometric chart

### Refrigerants
- 13 fluids: R32, R134a, R410A, R407C, R404A, R1234yf, R1234ze(E), R454B, R513A, R744, R290, R717, R600a
- Saturation from T or p (bubble / dew / mean temperature and glide for blends)
- Subcooled liquid, superheated vapour, supercritical (R744)
- Two-phase states from pressure and quality
- p-h diagram with the state point
- Pressure units: bar a, bar g, kPa, MPa, psig

## Methods and accuracy

| Section | Method | Validity |
|---|---|---|
| Water | Density: Kell (1975); cp: polynomial fitted to IAPWS-95 | 0–100 °C |
| MEG / MPG | Melinder (2010) polynomials, coefficients from CoolProp | freezing point to 100 °C |
| Moist air | ASHRAE Handbook – Fundamentals (2017), Ch. 1, ideal-gas model with Hyland-Wexler saturation pressure | standard HVAC range |
| Refrigerants | Tables generated with CoolProp (HEOS) and cubic Lagrange interpolation | −60 °C to ~160 °C, p ≤ 0.99·pc |

Refrigerant accuracy against CoolProp (820 test points below 0.9·pc): Tsat < 0.001 K, h < 0.06 kJ/kg, density < 0.03 %, cp < 0.4 %. Enthalpy and entropy use the IIR reference state (h = 200 kJ/kg, s = 1 kJ/kg·K for saturated liquid at 0 °C).

## Usage

Open the live link above, or download `index.html` and open it in your browser. It works fully offline.

## Disclaimer

This tool is intended for preliminary engineering calculations. Results are provided without warranty; verify critical values against a reference source before using them for design.

## About

Built with the help of AI (Claude by Anthropic). The engineering choices, references and validation were mine.

## Credits

- [CoolProp](http://www.coolprop.org/), Bell et al. (2014), *Ind. Eng. Chem. Res.* 53(6), 2498–2508 (MIT licence)
- Melinder, Å. (2010), *Properties of Secondary Working Fluids for Indirect Systems*, IIR
- Kell, G. S. (1975), *J. Chem. Eng. Data* 20(1), 97–105
- ASHRAE Handbook – Fundamentals (2017)