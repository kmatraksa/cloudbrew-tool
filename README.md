# Cloudbrew Pour Over Lab · Brewing Science Tools

> *ordinary is specialty*

A suite of precision brewing calculators and research frameworks for specialty coffee — built on extraction kinetics, mass-balance mathematics, and competition-level sensory science.

**Live site:** <https://kmatraksa.github.io/cloudbrew-tool/>

-----

## Tools

### ⚗️ Pour-by-Pour Calculator

Multi-stage extraction analyzer with per-fraction TDS input, SCA Brewing Control Chart visualization, and tail-cut diagnostic.

- Mass-balance framework: `M_coffee × EY = Y_out × TDS`
- Hidden Golden Cup formula: `TDS = EY / (R − 1.47)`
- Extraction Equivalency EY threshold (EEY ≈ 19%)
- Tail-cut thresholds from Batali et al. (2020)
- Auto-estimate kinetic model based on Liang et al. (2021)
- **Brew Log** — save every session, export CSV for research

### 🏗️ Coffee Architecture Blueprint Calculator

5-stage brewing architecture based on the Coffee Architecture Blueprint workshop (2025). Champion presets: Medina (WBrC 2023) and Peng (WBrC 2025).

- Thermal narrative visualization
- Water chemistry panel: Mg / Ca / HCO₃ (GH:KH = 3:1 WBrC target)
- CVA assessment: 15-pt descriptive + affective hedonic scoring
- Cooldown Experience: 65°C → 50°C → <45°C

### 📊 TDS → Ideal Cup Model

Input refractometer reading → instant SCA Brewing Control Chart position → diagnosis → dilution calculator.

### 🔬 Inside the Dripper *(EN / TH)*

Interactive visualization of coffee extraction — timeline scrubber, 20-molecule theater, dripper anatomy, V60 + Kalita Wave, pour deep-dive. Bilingual English/Thai.

### 📄 KBO-P Research Overview *(EN / TH)*

Plain-language companion to the KBO-P research manuscript — hypotheses, experimental design, 6 predicted figures, reviewer challenges. Bilingual.

-----

## Scientific Framework

|Parameter                     |Value          |Source              |
|------------------------------|---------------|--------------------|
|Water absorption coefficient X|1.47 g/g       |Lockhart (1957)     |
|Equivalency EY target (EEY)   |≈ 19%          |Happy (2025)        |
|Astringency zone              |19–22% EY      |Empirical           |
|Tail-cut threshold            |TDS_tail > 0.8%|Batali et al. (2020)|
|Arrhenius selectivity ratio   |1.87× (94→76°C)|KBO-P framework     |
|GH:KH water ratio target      |3:1            |WBrC 2024 trends    |

### Core Equation

```
M_coffee × EY = Y_out × TDS         (Lockhart 1957)

TDS / EY = 1 / (R − X)              where X ≈ 1.47 g/g
→ TDS = EY / (R − 1.47)             for ratio R = 15: TDS = EY / 13.53
```

### Extraction Equivalency Phenomenon

A brew whose TDS falls within the Golden Cup zone may still exhibit astringency when high-Eₐ compounds (CGA lactones, polyphenols) are disproportionately liberated. The EEY threshold (≈ 19%) marks the onset of this zone. KBO-P addresses this through thermal-selective kinetic suppression and mass-balance-derived tail-cut.

-----

## Research References

- Lockhart, E.E. (1957). *The soluble solids in beverage coffee as an index to cup quality.* Coffee Brewing Center.
- Hendon, C.H. et al. (2014). The role of dissolved cations in coffee extraction. *J. Agric. Food Chem.* 62(21).
- Batali, M.E. et al. (2020). Sensory analysis of full immersion and pour over brewed coffee. *Foods.*
- Liang, C. et al. (2021). An equilibrium desorption model for the strength and extraction yield of full immersion brewed coffee. *Sci. Rep.*
- Cameron, M.I. et al. (2020). Systematically improving espresso. *Matter* 2(3).
- Farah, A. et al. (2005). Effect of roasting on the formation of chlorogenic acid lactones. *J. Agric. Food Chem.* 53(5).

-----

## KBO-P Research

**Kinetic Bypass Over-Pour (KBO-P)** is a four-phase pour-over protocol exploiting the Arrhenius activation-energy spread between desirable and undesirable coffee compounds to achieve selective extraction without dual kettles or active temperature control.

Manuscript v2.0 available on request. Target journal: *Journal of Agricultural and Food Chemistry* (IF 4.8).

-----

## Project

**Cloudbrew Pour Over Lab** · Bangkok, Thailand  
KBO-P Research Platform · v2.0  
Built by Ford — specialty coffee practitioner and researcher
