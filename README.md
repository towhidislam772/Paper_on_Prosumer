# Prosumer Oriented Energy Sharing Model for Grid Integrated Electric Rickshaw Charging Garages

**ICMERE2025-PI-197**  
8th International Conference on Mechanical Engineering and Renewable Energy 2025  
10–12 November 2025, Chattogram, Bangladesh

---

## Authors

| Name | Department | Institution | Email |
|------|-----------|-------------|-------|
| Md. Towhidul Islam | Computer Science & Engineering | AIUB, Dhaka | 23-55036-3@student.aiub.edu |
| Shafayat Jamil | Computer Science & Engineering | AIUB, Dhaka | 23-55457-3@student.aiub.edu |
| Sajal Kumar Ghosh | Computer Science & Engineering | AIUB, Dhaka | 23-55419-3@student.aiub.edu |
| Anika Tabassum | Computer Science & Engineering | AIUB, Dhaka | 23-55070-3@student.aiub.edu |
| Bishwajit Banik Pathik *(Supervisor)* | Electrical & Electronic Engineering | AIUB, Dhaka | bishwajit@aiub.edu |

---

## Abstract

This paper proposes a **prosumer-oriented energy sharing model** for electric rickshaw charging garages, simulated using **HOMER Pro**. The system integrates solar photovoltaic (PV) arrays with the domestic electrical grid to form a hybrid energy system. Excess electricity is exported back to the grid, while grid imports supplement generation during low-solar periods. Simulation results demonstrate reduced greenhouse gas emissions, lower operational costs, and decreased reliance on the traditional grid. The bidirectional power flow enables the charging station to participate actively in the energy market as a prosumer, improving overall energy reliability.

---

## Keywords

`Prosumer` · `Energy Sharing` · `Electric Rickshaw Charging` · `Grid Integration` · `Renewable Energy` · `HOMER Pro` · `Solar PV` · `Smart Grid`

---

## Problem Statement

Electric rickshaws are rapidly growing in popularity across urban Bangladesh. Traditional grid-only charging garages face:
- High and unpredictable peak loads
- Erratic electricity supply
- High operational costs
- Significant greenhouse gas emissions

This work addresses these issues through a hybrid renewable energy approach.

---

## System Design

The prototype integrates four major components:

- **Solar PV Panels** — primary renewable energy source
- **Battery Storage** — backup and grid stability
- **Bidirectional Grid Connection** — for energy import/export
- **Electric Rickshaw Charging Terminals** — primary load

Power electronic converters and a software control algorithm manage energy distribution in real time.

### Control Logic (Algorithm Summary)

```
START
  Initialize system parameters (PV output, battery SOC, grid status, charging demand)
  LOOP each time step:
    Sense real-time energy data
    IF PV + Battery >= Demand:
      Use local energy → Update battery SOC
    ELSE:
      Draw from grid
    IF surplus energy available:
      Export to grid
    Check next time step
END
```

---

## Load Profile

### Daily Load Estimation

| Component | Rating & Usage | Quantity | Energy/Unit (kWh/day) | Total (kWh/day) |
|-----------|---------------|----------|-----------------------|-----------------|
| Rickshaw Charging | 4.06 kWh/day each | 10 | 4.06 | 40.60 |
| LED Lights | 10 W × 6 h | 10 | 0.06 | 0.60 |
| Mobile Charging | 10 W × 2 h | 10 | 0.02 | 0.20 |
| **Total** | | | | **41.40** |

- **Annual energy consumption:** 15,111 kWh/year
- **Peak instantaneous demand:** 6.87 kW (22:00–04:00, overlapping rickshaw charging + lighting)

### Hourly Load Distribution

| Hour Range | Rickshaw (kW) | Lights (kW) | Mobiles (kW) | Total (kW) |
|-----------|---------------|-------------|--------------|------------|
| 0–3 | 6.77 | 0.10 | 0.00 | 6.87 |
| 4–6 | 6.77 | 0.00 | 0.00 | 6.77 |
| 7–9 | 0.00 | 0.00 | 0.00 | 0.00 |
| 10–13 | 2.50 | 0.00 | 0.00 | 2.50 |
| 14–15 | 0.00 | 0.00 | 0.00 | 0.00 |
| 16–17 | 0.00 | 0.18 | 0.00 | 0.18 |
| 18–21 | 0.00 | 0.43 | 0.00 | 0.43 |
| 22–23 | 6.77 | 0.10 | 0.00 | 6.87 |

---

## Simulation & Results

Simulations were conducted in **HOMER Pro**, comparing four energy system configurations:

| Case | Description |
|------|-------------|
| **Case 1** | PV + Battery + Grid (Prosumer model) |
| **Case 2** | Grid-only (100% utility dependency) |
| **Case 3** | Revenue-maximizing PV + Grid (high CAPEX) |
| **Case 4** | Grid + Diesel generator backup (non-renewable) |

### Economic Comparison

| Case | NPC (৳) | LCOE (৳/kWh) | CAPEX (৳) | Operating Cost (৳/yr) | Grid Purchased (kWh) | Grid Sold (kWh) |
|------|---------|--------------|-----------|----------------------|---------------------|-----------------|
| 1 | 1,303,920 | **0.739** | 8,825,203 | -581,804 | 11,996 | 106,289 |
| 2 | 3,118,738 | 8.000 | 0 | 241,248 | 30,156 | 0 |
| 3 | 1.05E+07 | 5.949 | 1.43E+07 | -295,147 | 11,996 | 106,550 |
| 4 | 1.24E+07 | **31.74** | 5,517,265 | 530,313 | 30,155 | 0 |

**Key finding:** Case 1 achieves the lowest LCOE (0.739 ৳/kWh) and generates net revenue by selling surplus energy to the grid, while achieving positive cumulative cash flow over a 25-year horizon.

---

## Conclusions

- The hybrid PV–battery–grid system effectively optimizes renewable usage and maintains continuous load supply.
- Case 1 (prosumer model) is the most economically and operationally favorable configuration.
- The system reduces grid dependency and greenhouse gas emissions compared to grid-only and diesel-backup scenarios.
- Future work should involve real hardware deployment and testing under varied real-world conditions.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| HOMER Pro | Hybrid energy system simulation and optimization |
| Solar PV Arrays | Renewable energy generation modelling |

---

## Nomenclature

| Symbol | Meaning |
|--------|---------|
| PV | Photovoltaic |
| NPC | Net Present Cost |
| LCOE | Levelized Cost of Energy |
| CAPEX | Capital Expenditure |
| OPEX | Operational Expenditure |
| SOC | State of Charge |
| EV | Electric Vehicle |
| PHEV | Plug-in Hybrid Electric Vehicle |
| PEV | Plug-in Electric Vehicle |
| HOMER Pro | Hybrid Optimization of Multiple Energy Resources |

---

## Citation

If you reference this work, please cite:

> Md. Towhidul Islam, Shafayat Jamil, Sajal Kumar Ghosh, Anika Tabassum, and Bishwajit Banik Pathik, "Prosumer Oriented Energy Sharing Model for Grid Integrated Electric Rickshaw Charging Garages," *Proceedings of the 8th International Conference on Mechanical Engineering and Renewable Energy 2025 (ICMERE2025)*, Chattogram, Bangladesh, November 10–12, 2025, Paper ID: ICMERE2025-PI-197.

---

*© ICMERE2025 — American International University-Bangladesh*
