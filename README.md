# Hydrogen Wettability Prediction

Long-term underground hydrogen storage is influenced by several interrelated factors, including rock and rock wettability, capillary entry pressure, sealing performance, chemical interactions between hydrogen and formation fluids or minerals, and potential microbial activity. Among these, wettability has been a key focus due to its strong effect on capillary trapping behavior and its role in maintaining storage integrity.


# 1. Purpose of This Study

This work addresses key challenges in hydrogen wettability prediction and underground storage assessment by:

- **Developing transparent symbolic models** using Genetic Programming (GP) and Group Method of Data Handling (GMDH), offering interpretability in contrast to conventional black-box machine learning approaches.
- **Incorporating multicomponent gas effects**, including nitrogen, methane, and carbon dioxide, as well as variations in brine salinity, to better reflect realistic subsurface conditions.
- **Benchmarking model performance** by comparing interpretability and predictive accuracy against previously published data-driven studies.
- **Deploying an easy-to-use graphical interface** that enables users to apply these models for practical underground hydrogen storage analysis.

---


# 2. HyWEC: Hydrogen Wettability Estimation via Contact Angle

## a. Overview

**HyWEC** (Hydrogen Wettability Estimation via Contact Angle) is a standalone graphical user interface (GUI) developed to enable rapid and interpretable predictions of hydrogen wettability on quartz surfaces. It is optimized for scenarios involving cushion gases like nitrogen, methane, and carbon dioxide under susbsurface conditions.

Unlike traditional black-box models [1-5], HyWEC utilizes **symbolic regression models** based on **Genetic Programming (GP)** and the **Group Method of Data Handling (GMDH)**. This results in **explicit, algebraic equations** that are easier to interpret and verify, making the tool suitable for both research and field application.

---

## b. Core Functionality

HyWEC accepts the following user-defined input parameters:

| **Parameter**            | **Input Range**         |
|--------------------------|-------------------------|
| Pressure (MPa)           | 0.69 – 20.68            |
| Temperature (K)          | 295 – 343               |
| Salinity (mol/kg)        | 0 – 3.42                |
| Nitrogen mole fraction (mol%)  | 0 – 70                  |
| Methane mole fraction (mol%) | 0 – 80                  |
| Carbon dioxide mole fraction (mol%) | 0 – 40                  |

**Workflow:**
1. Choose a model from the **"Select model or correlation"** dropdown.
2. Enter all required parameters.
3. Click **"Predict"** to estimate the contact angle.

HyWEC validates inputs and prevents prediction if:
- Inputs are non-numeric or negative.
- Parameters fall outside supported ranges (e.g., Pressure < 0.69 MPa).
- Cushion gas compositions exceed allowable mole fractions.

---

## c. Advantages

- **Transparent modeling**: Users can view and interpret model equations.
- **Cross-validated performance**: Symbolic models were trained on stratified data splits and validated against literature results (e.g., Table 6 in the main paper).
- **Quick scenario evaluation**: Engineers can rapidly assess wettability shifts under new operational conditions.

---

## d. Limitations

- **Domain-bound accuracy**: Models are more reliable within trained input spaces.
- **No retraining**: User-defined model training or customization is not currently supported.
- **Static equation structure**: Equations are fixed and cannot adapt to inputs outside their descriptors.

---

## e. Use Case Example

**Input:**
- Pressure: `3 MPa`
- Temperature: `323 K`
- Salinity: `1.709 mol/kg`
- Nitrogen, Methane, Carbon dioxide mole fractions: `0%` each

**Output:**
- Predicted contact angle: `38.91°`
- Reported experimental value: `40.8°` [6]  
- Deviation: `4.6%` below experimental observation

## HyWEC Interface
![HyWEC GUI](https://github.com/JNTurkson/Hydrogen-Wettability-Prediction/blob/main/HyWEC.jpg)
---

## f. Future Improvements

Planned enhancements include:
- Broader parameter ranges and mineral surface types.
- Interactive plots showing contact angle trends.
- Full web-based version for community access and feedback.

---

## Citation

Please cite the associated publication as (To Be Added Later).
---

## References

1. **Nassabeh, M.**, You, Z., Keshavarz, A., & Iglauer, S. (2025). *Data-driven strategy for contact angle prediction in underground hydrogen storage using machine learning*. **Journal of Energy Storage**, 114, 115908. [https://doi.org/10.1016/j.est.2025.115908](https://doi.org/10.1016/j.est.2025.115908)

2. **Maleki, M.**, Dehghani, M.R., Akbari, A., Kazemzadeh, Y., & Ranjbar, A. (2024). *Investigation of wettability and IFT alteration during hydrogen storage using machine learning*. **Heliyon**, 10(19). [https://doi.org/10.1016/j.heliyon.2024.e38679](https://doi.org/10.1016/j.heliyon.2024.e38679)

3. **Tariq, Z.**, Ali, M., Yekeen, N., Baban, A., Yan, B., Sun, S., & Hoteit, H. (2023). *Enhancing wettability prediction in the presence of organics for hydrogen geo-storage through data-driven machine learning modeling of rock/H₂/brine systems*. **Fuel**, 354. [https://doi.org/10.1016/j.fuel.2023.129354](https://doi.org/10.1016/j.fuel.2023.129354)

4. **Vo Thanh, H.**, Rahimi, M., Dai, Z., Zhang, H., & Zhang, T. (2023). *Predicting the wettability rocks/minerals-brine-hydrogen system for hydrogen storage: Re-evaluation approach by multi-machine learning scheme*. **Fuel**, 345. [https://doi.org/10.1016/j.fuel.2023.128183](https://doi.org/10.1016/j.fuel.2023.128183)

5. **Mwakipunda, G.C.**, Ibrahim, A.-W., Kouassi, A.K.F., Nafouanti, M.B., & Yu, L. (2025). *Improving wettability estimation in carbonate formation using machine learning algorithms: Implications for underground hydrogen storage applications*. **International Journal of Hydrogen Energy**, 111, 781–797. [https://doi.org/10.1016/j.ijhydene.2025.02.342](https://doi.org/10.1016/j.ijhydene.2025.02.342)

6. **Alanazi, A.**, Al-Yaseri, A., Mowafi, M., Leila, M., & Hoteit, H. (2023). *First assessment of hydrogen/brine/Saudi basalt wettability: Implications for hydrogen geological storage*. **Frontiers in Earth Science**, 11. [https://doi.org/10.3389/feart.2023.1225131](https://doi.org/10.3389/feart.2023.1225131)

---
