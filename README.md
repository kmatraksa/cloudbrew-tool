# Cloudbrew Pour Over Lab · Brewing Science Tools

> *ordinary is specialty*

A suite of precision brewing calculators and research frameworks for specialty coffee — built on extraction kinetics, mass-balance mathematics, and competition-level sensory science.

**Live site:** <https://kmatraksa.github.io/cloudbrew-tool/>

-----

## Tools

### 🎯 Flavor Targeting Calculator *(NEW)*

Recipe design tool — select a target on the SCA Brewing Control Chart, choose a Flavor Direction, and receive a complete recipe instantly.

- **Interactive SCA chart** — tap to place your extraction target
- **Flavor Direction** — Very Sour / Sour / Balanced / Sweet / Very Sweet
- **Exact recipe math:** `Ratio = EY/TDS + 1.47` · `Yield = Dose × EY/TDS`
- **Pour schedule** auto-calculated with per-pour TDS estimate (kinetic model)
- **Temperature strategy** per flavor direction (5 profiles, Peng framework)
- **Dilution flavor model** — Acidity drops 1.2×, Sweetness drops 0.8× on dilution
- Grind size recommendation based on target zone
- Cooldown Experience: 65°C → 50°C → <45°C

### ⚗️ Pour-by-Pour Calculator

Multi-stage extraction analyzer with per-fraction TDS input, SCA Brewing Control Chart visualization, tail-cut diagnostic, and brew logging.

- Mass-balance framework: `M_coffee × EY = Y_out × TDS`
- Hidden Golden Cup formula: `TDS = EY / (R − 1.47)`
- Extraction Equivalency EY threshold (EEY ≈ 19%) with gauge warning
- Tail-cut diagnostic: TDS_tail > 0.8% → cut (Batali et al., 2020)
- Auto-estimate kinetic model based on Liang et al. (2021)
- Grind size selector affects extraction speed (k multiplier)
- **Brew Log** — save every session, export CSV for research

### 🏗️ Coffee Architecture Blueprint Calculator

5-stage brewing architecture based on the Coffee Architecture Blueprint workshop (2025). Champion presets: Medina (WBrC 2023) and Peng (WBrC 2025).

- Thermal narrative visualization per stage
- Water chemistry panel: Mg / Ca / HCO₃ (GH:KH = 3:1 WBrC target)
- CVA assessment: 15-pt descriptive + affective hedonic scoring
- Cooldown Experience: 65°C → 50°C → <45°C

### 📊 TDS → Ideal Cup Model

Input refractometer reading → instant SCA Brewing Control Chart position → diagnosis → adjustment calculator.

- Real-time dot on SCA chart
- EEY zone warning at 19% and 21%
- Option A/B: adjust yield or dose to hit target TDS 1.40%

### 🔬 Inside the Dripper *(EN / TH)*

Interactive visualization of coffee extraction — timeline scrubber, 20-molecule theater, dripper anatomy, V60 + Kalita Wave, pour deep-dive. Bilingual English/Thai.

### 📄 KBO-P Research Overview *(EN / TH)*

Plain-language companion to the KBO-P research manuscript — hypotheses, experimental design, 6 predicted figures, reviewer challenges. Bilingual English/Thai.

-----

## Accuracy Model

Each calculation is labelled by confidence level:

|Label         |Meaning                               |Examples                          |
|--------------|--------------------------------------|----------------------------------|
|✅ **EXACT**   |Pure mass-balance math, no assumptions|Ratio, Water, Yield               |
|⚠️ **ESTIMATE**|Kinetic model, empirically calibrated |Pour TDS, Tail cut, Flavor profile|

The kinetic model uses the equilibrium extraction form from Liang et al. (2021): `TDS_i = (remaining × w/(w + k·D)) / yield_out` with per-pour resistance constants calibrated to match observed pour-over TDS patterns.

-----

## Scientific Framework

|Parameter                     |Value          |Source               |
|------------------------------|---------------|---------------------|
|Water absorption coefficient X|1.47 g/g       |Lockhart (1957)      |
|Equivalency EY target (EEY)   |≈ 19%          |Happy Workshop (2025)|
|Astringency zone              |19–22% EY      |Empirical            |
|Tail-cut threshold            |TDS_tail > 0.8%|Batali et al. (2020) |
|Arrhenius selectivity ratio   |1.87× (94→76°C)|KBO-P framework      |
|GH:KH water ratio target      |3:1            |WBrC 2024 trends     |
|Dilution: acidity factor      |1.2×           |Sensory science      |
|Dilution: sweetness factor    |0.8×           |Sensory science      |

### Core Equations

```
M_coffee × EY = Y_out × TDS                    (conservation of solubles, Lockhart 1957)

TDS / EY = 1 / (R − X)    where X ≈ 1.47 g/g  (hidden Golden Cup formula)

Ratio    = EY / TDS + X                         (recipe design from target)
Yield    = Dose × EY / TDS                      (target liquid output)
X_actual = (Water_in − Yield_out) / Dose        (empirical calibration per roast)
EY_main  = (TDS_blend × Y_total − TDS_tail × Y_tail) / Dose   (pre-tail EY check)
```

### Extraction Equivalency Phenomenon

A brew whose TDS falls within the Golden Cup zone may still exhibit astringency when high-Eₐ compounds (CGA lactones, polyphenols) are disproportionately liberated relative to desirable low-Eₐ compounds (organic acids, sucrose). The EEY threshold (≈ 19%) marks the onset of this zone. Formally defined in KBO-P Manuscript v2.0 (§1.3).

-----

## Research References

- Lockhart, E.E. (1957). *The soluble solids in beverage coffee as an index to cup quality.* Coffee Brewing Center.
- Hendon, C.H. et al. (2014). The role of dissolved cations in coffee extraction. *J. Agric. Food Chem.* 62(21).
- Batali, M.E. et al. (2020). Sensory analysis of full immersion and pour over brewed coffee. *Foods.*
- Liang, C. et al. (2021). An equilibrium desorption model for the strength and extraction yield of full immersion brewed coffee. *Sci. Rep.*
- Cameron, M.I. et al. (2020). Systematically improving espresso. *Matter* 2(3).
- Farah, A. et al. (2005). Effect of roasting on the formation of chlorogenic acid lactones. *J. Agric. Food Chem.* 53(5).
- Happy Workshop (2025). *Brewing for Competition.* Brew Whale BKK, Bangkok.

-----

## KBO-P Research

**Kinetic Bypass Over-Pour (KBO-P)** is a four-phase pour-over protocol exploiting the Arrhenius activation-energy spread between desirable and undesirable coffee compounds to achieve selective extraction without dual kettles or active temperature control.

Key contributions of v2.0 manuscript:

- Formal definition of the **Extraction Equivalency Phenomenon**
- Derivation of hidden Golden Cup mass-balance relationship `TDS/EY = 1/(R−X)`
- Multi-pulse extraction efficiency proof (n+1 pours > n pours at constant time)
- Tail-cut diagnostic protocol using TDS_tail as compound-class proxy
- Empirical X_actual calibration from scale measurement only

Manuscript v2.0 available on request. Target journal: *Journal of Agricultural and Food Chemistry* (IF 4.8).

-----

## Files

|File                                 |Description                     |
|-------------------------------------|--------------------------------|
|`index.html`                         |Landing page                    |
|`flavor_targeting_calculator.html`   |Recipe design from flavor target|
|`pour_by_pour_calculator.html`       |Per-fraction analysis + brew log|
|`coffee_architecture_calculator.html`|Competition blueprint           |
|`sca_brewing_calculator.html`        |TDS → ideal cup                 |
|`inside_the_dripper.html`            |Interactive visualization EN/TH |
|`kbo_p_research_overview.html`       |Research companion EN/TH        |
|`happy_workshop_cheatsheet.html`     |Workshop summary cheatsheet     |
|`README.md`                          |This file                       |

-----

## Project

**Cloudbrew Pour Over Lab** · Bangkok, Thailand  
KBO-P Research Platform · v2.1  
Built by Ford — specialty coffee practitioner and researcher

*“The cup is not the destination. It is the architecture of the experience.”*
