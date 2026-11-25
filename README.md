# KSA Solar Thermal Radiation Models

Solar radiation flux, HVAC cooling-load reduction and window-film thermal efficiency equations for buildings and vehicles in Saudi Arabia (Jeddah climate).

Peak direct solar flux on glazed facades in Jeddah exceeds roughly 850 W/m2 in summer. Unfilmed glass is a dominant share of the internal cooling load of villas and offices; the formulas in this repository estimate the saving from solar-control window film.

## Quick model

- Solar heat gain through glass: Q = A x I x SHGC
- Cooling-load reduction: dQ = A x I x (SHGC_before - SHGC_after)
- Estimated yearly saving: dQ x cooling hours / COP

```python
def cooling_saving_kwh(area_m2, peak_flux=850, shgc_before=0.80, shgc_after=0.30, hours=1800, cop=3.0):
    dq_kw = area_m2 * peak_flux * (shgc_before - shgc_after) / 1000
    return dq_kw * hours / cop
```

## Resources (AzelCore, Jeddah)

- [Thermal insulation and AC saving calculator](https://azelcore.com/calculator)
- [KSA thermal insulation and solar radiation engineering report 2026](https://azelcore.com/research/ksa-thermal-report-2026)
- [AzelCore - authorized 3M and Johnson film center in Jeddah](https://azelcore.com)

## Contact

AzelCore, King Fahd Road, Al-Zahra District, Jeddah 23425, Saudi Arabia - +966 56 461 2017 - https://azelcore.com
