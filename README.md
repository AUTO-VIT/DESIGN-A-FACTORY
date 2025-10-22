# 🧱 DESIGN A FACTORY – BRICK EDITION
**Gamified Technical Event | Technovit 2025**

---

## OBJECTIVE
Build your own **brick factory** and achieve **at least 27,000 finished bricks/hour** at the **lowest cost** and with **high reliability**.

Your design must include the following production stages:
1. **Raw Preparation → Mixers**
2. **Shaping → Extruders**
3. **Drying + Firing**
4. **Final Handling → Packaging**

Each stage must be sized carefully so the **slowest stage** doesn’t limit your production rate.

---

## HOW TO PLAY
- You will choose **one machine per stage**, except:
  - **Extrusion:** requires **two or more** parallel machines.
  - **Packaging:** can have **one or more** parallel machines.
- Firing is built into the **Drying + Firing** stage — it will not be a bottleneck.
- You must stay **within the total budget of 12 cost points**.
- The **factory throughput** is the **minimum effective capacity** of all stages.
- The **winner** is the team that:
  1. Meets or exceeds 27,000 bricks/hour,
  2. Stays within the budget,
  3. Has the **lowest cost** and **highest reliability**.

---

## MACHINE CATALOG

### Stage 1: Raw Preparation – Mixers (pick **exactly 1**)
| Model | Description | Cap. (bricks/hr) | Uptime | Eff. Cap. | Cost | Fail% |
|--------|--------------|----------------:|-------:|-----------:|-----:|------:|
| **Normal Mixer** | Basic twin-shaft | 32,000 | 0.88 | **28,160** | 2 | 1.5 |
| **Alpha Mixer** | Reinforced paddles | 34,000 | 0.90 | **30,600** | 3 | 2.0 |
| **Beta Mixer** | High-torque heavy-duty | 38,000 | 0.92 | **34,960** | 4 | 3.0 |

>  Any single mixer can meet the required output.

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

##  RULES SUMMARY

| Rule | Description |
|------|--------------|
| Mixer | Pick **exactly one** model |
| Extruder | Must use **≥2 units** in parallel |
| Drying + Firing | Pick **exactly one** option |
| Packaging | One or more units allowed |
| Target | All stages ≥ **27,000 bricks/hour** |
| Budget Cap | **Total Cost ≤ 12 points** |
| Winner | Lowest total cost; tiebreaker = higher reliability |

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
- Background losses (drying shrinkage 5%, ignition 3%) are simulated internally.  
- Firing is oversized and will not bottleneck output.  
- Players only balance **capacity**, **cost**, and **reliability**.  
- You can introduce **random events** (e.g., breakdowns or surges) in bonus rounds.

---

