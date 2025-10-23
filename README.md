# 🧱 DESIGN A FACTORY – BRICK EDITION

## OBJECTIVE
Design and optimize your own **brick factory** to meet a **target annual output** while balancing **capacity, reliability, and cost**.

Your design must include the following production stages:
1. **Raw Preparation → Mixers**
2. **Shaping → Extruders**
3. **Drying + Firing**
4. **Final Handling → Packaging**

- **Annual Target Output:** 200,000,000 finished bricks/year  
- **Working Days:** 350 days/year  
- **Shifts per Day:** 3  
- **Hours per Shift:** 7  
- **Total Working Hours per Year:** 7,350 hr/year  
- **Required Dispatch Rate:** **≈ 27,000 finished bricks/hour**

Your goal is to design a factory that **reaches or exceeds** this throughput while staying **within budget** and maintaining **reliability**.
Each stage must be sized carefully so the **slowest stage** doesn’t limit your production rate.

---

## HOW TO PLAY
- You will choose **one machine per stage**, except: (not to share to players)
  - **Extrusion:** requires **two or more** parallel machines.
  - **Packaging:** can have **one or more** parallel machines.
- Firing is built into the **Drying + Firing** stage — it will not be a bottleneck.
- You must stay **within the total budget of 12 cost points**. (can share)
- The **factory throughput** is the **minimum effective capacity** of all stages. (can share)
- The **winner** is the team that: (or other parameter)
  1. Meets or exceeds 27,000 bricks/hour,
  2. Stays within the budget,
  3. Has the **lowest cost** and **highest reliability**.

---

## MACHINE CATALOG

### Stage 1: Raw Preparation – Mixers (pick **1** dot share this to player)

| Model | Description | Input Capacity (tons/hr clay) | Uptime | **Eff. Cap. (tons/hr)** | Cost | Fail% |
|--------|--------------|----------------:|-------:|-----------:|-----:|------:|
| **Normal Mixer** | Basic twin-shaft | 60 | 0.88 | **52.8** | 2 | 1.5 |
| **Alpha Mixer** | Reinforced paddles | 68 | 0.90 | **61.2** | 3 | 2.0 |
| **Beta Mixer** | High-torque heavy-duty | 78 | 0.92 | **71.8** | 4 | 3.0 |

> Each ton of clay ≈ **353 green bricks** after shaping and moisture adjustment.

---

### Stage 2: Shaping – Extruders (parallel **required**)
| Model | Description | Cap. (bricks/hr) | Uptime | Eff. Cap./unit | Cost (each) | Fail% |
|--------|--------------|----------------:|-------:|----------------:|-------------:|------:|
| **EX-S** | Single-screw economy | 16,000 | 0.88 | **14,080** | 2 | 1.8 |
| **EX-A** | Auto vacuum extruder | 20,000 | 0.90 | **18,000** | 3 | 2.5 |
| **EX-T** | Twin-screw heavy-duty | 24,000 | 0.88 | **21,120** | 4 | 3.5 |

>  You **must** use at least two extruders in parallel to reach 27,000/hr.

---

### Stage 3: Drying + Firing (pick **exactly 1**)
| Model | Description | Cap. (bricks/hr) | Uptime | Eff. Cap. | Cost | Fail% | Notes |
|--------|--------------|----------------:|-------:|-----------:|-----:|------:|-------|
| **Room Firing** | Traditional firing room only | 31,000 | 0.88 | **27,280** | 2 | 4.0 | Least reliable |
| **Chamber Dry+Fire** | Controlled chamber drying & firing | 33,000 | 0.90 | **29,700** | 3 | 2.5 | Balanced |
| **Tunnel Dry+Fire** | Fully automated tunnel dryer + kiln | 36,000 | 0.92 | **33,120** | 6 | 1.2 | Most reliable, very costly |

>  Choosing the **Tunnel** setup will leave little budget for multiple extruders.

---

### Stage 4: Final Handling – Packaging (1 or more)
| Model | Description | Cap. (bricks/hr) | Uptime | Eff. Cap./unit | Cost | Fail% |
|--------|--------------|----------------:|-------:|----------------:|-----:|------:|
| **PK-B** | Basic palletizer | 30,000 | 0.92 | **27,600** | 2 | 1.0 |
| **PK-L** | Line palletizer | 36,000 | 0.90 | **32,400** | 3 | 2.0 |
| **PK-D** | Dual-lane palletizer | 44,000 | 0.88 | **38,720** | 4 | 3.0 |

> One packer usually suffices, but adding a second increases reliability.

---

##  EXAMPLES

###  **Balanced Factory (Recommended Build)**
| Stage | Choice | Units | Stage Cap. (bricks/hr) | Cost |
|--------|---------|--------|----------------:|------:|
| Mixer | Normal | 1 | 28,160 | 2 |
| Extruders | EX-S | 2 | 28,160 | 4 |
| Dry+Fire | Chamber | 1 | 29,700 | 3 |
| Packaging | PK-B | 1 | 27,600 | 2 |
| **Total** |  |  | **27,600/hr ✅** | **11 ≤ 12 ✅** |

>  Meets target, within budget, good reliability.

---

###  **Tunnel Trap (Fails Budget)**
| Stage | Choice | Units | Cap. | Cost |
|--------|---------|--------|------:|------:|
| Mixer | Normal | 1 | 28,160 | 2 |
| Extruders | EX-A | 2 | 36,000 | 6 |
| Dry+Fire | Tunnel | 1 | 33,120 | 6 |
| Packaging | PK-B | 1 | 27,600 | 2 |
| **Total** |  |  | **27,600/hr ✅** | **16 ❌ Over Budget** |

>  Too costly — can’t afford two extruders if Tunnel is used.

---

## 🏁 SCORING
1. **Throughput Gate:** every stage ≥ 27,000/hr  
2. **Budget Gate:** total cost ≤ 12  
3. **Ranking:**  
   - Lowest cost wins  
   - Tiebreaker: higher reliability (sum of Fail% is lower)  
   - Optional bonus: simplest configuration (fewest models)

---

##  BEHIND THE SCENES (organizer-only logic)

<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/12d18845-0d12-4eb3-8903-2241117efc51" />

- Background losses (drying shrinkage 5%, ignition 3%) are simulated internally.  
- Firing is oversized and will not bottleneck output.  
- Players only balance **capacity**, **cost**, and **reliability**.  
- You can introduce **random events** (e.g., breakdowns or surges) in bonus rounds.

These calculations run **in the background** of the game.  
Players will only pick machines, but the simulation internally converts **tons of clay input → finished fired bricks** using the following parameters and flow.

### Step 1: Constants
| Parameter | Symbol | Value | Notes |
|------------|--------|--------|-------|
| Clay density | ρ | 2000 kg/m³ | Average clay solids |
| Green brick moisture | M₍g₎ | 15% | Water before drying |
| Drying shrinkage | S₍d₎ | 5% | Volume/mass loss |
| Ignition loss | L₍f₎ | 3% | Burnout in firing |
| Working hours/year | H₍y₎ | 7350 hr | (350 days × 3 × 7) |
| Target output | B₍y₎ | 200M bricks | Annual requirement |

---

### Step 2: Unit Conversions
| Stage | Input | Output | Conversion |
|--------|--------|---------|------------|
| Mixer | tons clay | green bricks | 1 ton = 353 bricks |
| Extrusion | green bricks | shaped bricks | ×0.85 |
| Drying | shaped → dry | ×0.95 |
| Firing | dry → fired | ×0.97 |

---

### Step 3: Backend Flow
```text
Green_bricks = Mixer_eff_cap × 353
Shaped_bricks = Green_bricks × 0.85
Dry_bricks = Shaped_bricks × 0.95
Fired_bricks = Dry_bricks × 0.97
Dispatch = min(Stage capacities)
```
Step 4: Reliability Simulation

Each stage has a Fail% per hour.
For multiple units (extruders, packaging):

Effective Fail% = (Fail%) / (number of units)


Random breakdown event (optional):

if random() < Fail%:
    output = output * 0.8

Step 5: Scoring Logic
if (min(Stage caps) >= 27000) and (TotalCost <= 12):
    score = (Output / 27000) * (Reliability / Cost)
else:
    score = 0

Step 6: Dynamic Event Ideas

Breakdown: one machine temporarily down (simulate Fail%)

Demand Surge: temporary target = 30,000/hr

Energy Cap: disable one dryer or extruder

Rush Order: must reconfigure for new target under 5 minutes

Step 7: Programmer Output Variables
Variable	Unit	Formula
InputClay_tph	tons/hr	Mixer_eff_cap
GreenBricks_hr	bricks/hr	InputClay_tph × 353
DryBricks_hr	bricks/hr	GreenBricks_hr × 0.85 × 0.95
FiredBricks_hr	bricks/hr	DryBricks_hr × 0.97
FinalOutput_hr	bricks/hr	min(Stage caps)
AnnualOutput	bricks/year	FinalOutput_hr × 7350


---

# this is an example for how we should make a data sheet.

##  MATERIAL AND PROCESS BASICS
Your factory converts **raw clay** into **fired bricks**.

| Stage | Process Description | Material Form | Units Used |
|-------|----------------------|----------------|-------------|
| **1. Mixing** | Prepares clay mass with uniform composition | Wet clay | Tons/hour |
| **2. Extrusion** | Shapes clay into wet bricks | Green bricks | Tons/hour → bricks/hour |
| **3. Drying + Firing** | Removes moisture and bakes to final hardness | Dry/Fired bricks | Bricks/hour |
| **4. Packaging** | Sorts, stacks, and dispatches | Finished bricks | Bricks/hour |

---

### MATERIAL CONVERSION LOGIC (used internally)
| Factor | Value | Effect |
|--------|--------|--------|
| Green brick moisture | 15% | Adds mass during mixing/extrusion |
| Drying shrinkage | 5% | Volume/mass loss during drying |
| Ignition loss | 3% | Weight loss during firing |
| Clay density | 2,000 kg/m³ | Used for ton calculations |

> The simulator automatically converts **tons of clay input → fired bricks output** 
> Players only see machine choices and effective capacities.

---


## UNDERSTANDING “UPTIME” AND “EFFECTIVE CAPACITY”  

| Term | Meaning | Example |
|------|----------|----------|
| **Uptime** | The fraction of total time a machine is expected to be operational (accounts for maintenance or breakdowns). | 0.90 uptime = 90% available during operation. |
| **Eff. Cap.** | The *actual usable capacity*, calculated as:<br>**Eff. Cap. = Nameplate Capacity × Uptime** | 34,000 × 0.90 = **30,600** bricks/hr. |

> Real factories never run at 100%. Downtime reduces effective capacity and impacts planning.

---

