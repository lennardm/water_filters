# Swapping a Kinetico Valve Controller for a Clack WS1TT

## A practical guide for Kinetico 4060 M/T, 4060s OD MAC and similar twin-tank systems

---

## Background & Why This Guide Exists

Kinetico water treatment systems are well-engineered and long-lasting — but their valve heads are proprietary, expensive (€400–800+), and increasingly difficult to source in Sweden and much of Europe. When the valve controller fails, many owners are told to replace the entire system.

This guide explains how to replace the Kinetico valve head with a **Clack WS1TT**, an industry-standard twin-tank control valve that is widely available, fully documented, and inexpensive to service. The Clack WS1TT is a direct functional replacement for Kinetico twin-tank systems and can replicate all regeneration functions including countercurrent (upflow) regeneration.

> ⚠️ This guide was developed for the **Kinetico 4060 M/T** (anion/cation mixed-bed resin + Macrolite upper tanks). Most principles apply to other 4060s variants. Always verify specifications for your specific model.

---

## Understanding Your Kinetico System

Before starting, identify your model. The main variants are:

| Model | Upper tanks | Lower tanks | Service flow | Regen flow |
|---|---|---|---|---|
| 4060s OD MAC | Macrolite (5 micron filter) | Standard cation resin | Downflow | Countercurrent (upflow) |
| 4060s OD AC | Activated carbon | Standard cation resin | Downflow | Countercurrent (upflow) |
| 4060 M/T | Macrolite | Anion/cation mixed resin | Downflow | Countercurrent (upflow) |
| 4040s OD | Fine mesh cation resin | Activated carbon | Upflow | Countercurrent |

**All these models use countercurrent regeneration** — brine flows opposite to the normal service flow direction. This is important for Clack configuration.

### Key Kinetico specs (4060s OD MAC / 4060 M/T)

| Parameter | Value |
|---|---|
| Tank size (upper) | 2× 8" × 17" |
| Tank size (lower) | 2× 8" × 24" |
| Backwash flow control | 3.00 GPM (4060s OD MAC) |
| Brine refill flow control | 0.40 GPM |
| Salt dose per regen | ~4.4 lbs / ~2.0 kg |
| Regen volume | 65 gallons / 246 litres |
| Regen time | 40 minutes |
| Venturi throat (OD MAC) | Orange, part 10060 |
| Venturi throat (M/T) | Likely white (confirm on your unit) |

---

## Tools & Parts Required

### Clack WS1TT parts to order

- **Clack WS1TT CI control valve** (the CI controller supports upflow brining — verify "Up Brine" option in programming menu)
- **Upflow piston** — must match the "Up Brine" software setting; physically different from downflow piston
- **DLFC (Drain Line Flow Control) disc: 3.0 GPM** — matches Kinetico backwash spec
- **Injector set** — start with **A (black)** for 8" upflow configuration; have B (yellow) available as backup
- **BLFC (Brine Line Flow Control): 0.40 GPM** — may be built into brine valve assembly; confirm on your unit
- Standard O-ring/seal kit for WS1TT
- Bypass valve (if not included)

### Tools
- Adjustable wrench / pipe wrenches
- Bucket (10–20 litres) for brine draw test
- Saturated brine solution (~265 g/L NaCl) for testing
- Stopwatch
- Measuring jug

---

## Step 1: Benchmark the Kinetico Venturi Before You Remove It

This is the most important step. Rather than guessing injector size, **measure the actual brine draw rate of your Kinetico valve** so you can match it exactly on the Clack.

1. Fill a bucket with **saturated brine** (~265 g/L — dissolve salt in water until no more dissolves)
2. Connect the Kinetico valve's brine inlet to the bucket
3. Run the system at normal operating pressure with the Kinetico valve in **brine draw cycle**
4. **Measure:** volume drawn per minute (litres/min)
5. **Measure:** total draw time until air is sucked in (all brine exhausted)
6. Note: above ~40 PSI (2.75 bar) the venturi draw rate plateaus, so exact pressure is not critical

> **Why this matters:** The Clack injector controls brine draw rate. If you choose an injector that draws too fast for anion/cation resin, regeneration will be incomplete. If it draws too slowly, cycle times become impractical. Matching the Kinetico rate gives you a proven starting point.

Also note the **venturi throat colour** when disassembling the Kinetico valve:
- Orange = standard cation/Macrolite variant (part 10060)
- White = smaller orifice, likely M/T or similar variant (part 1043)
- White suggests slower draw rate → lean toward smaller Clack injector

---

## Step 2: Identify the Correct Clack Injector

Cross-reference your measured brine draw rate (litres/min) against the Clack WS1TT injector flow rate table in the service manual (page varies by edition). 

For **8" tanks, upflow regeneration**, the WS1TT manual table recommends:

| Injector | Colour | Application |
|---|---|---|
| A | Black | 8" upflow — starting recommendation |
| B | Yellow | 10" upflow / next size up if A draws too slowly |

**For anion/cation mixed resin (M/T model):** slower brine draw is preferable for better contact time. If your bucket test gives a lower flow rate than injector A produces, consider restricting via the BLFC disc rather than upsizing the injector.

**Cold water note (5–10°C):** Cold water is more viscous. In an upflow configuration, this increases hydraulic pressure on the resin bed, so do not go larger than necessary to avoid bed lifting (though bed lifting is largely self-limiting when resin is in the lower tank with Macrolite above).

---

## Step 3: Configure the Clack WS1TT

### Physical configuration

1. Install the **upflow piston** in the valve body (not the standard downflow piston)
2. Install the chosen **injector (A/black)** in the **"UP" port** on the valve body
3. Install a **plug** in the "DN" port
4. Install the **3.0 GPM DLFC disc** in the drain line fitting
5. Install or verify the **0.40 GPM BLFC** in the brine line fitting (may be pre-installed in brine valve assembly)

### Controller programming (CI controller)

Enter master programming mode and set:

| Parameter | Setting |
|---|---|
| System type | Twin alternating softener |
| Brine/slow rinse cycle | **Up Brine** (not Dn Brine) |
| Brine draw time | From bucket test — total minutes to draw 65 gallons / 246 litres |
| Backwash time | ~10 minutes (adjust to match media spec) |
| Regeneration initiation | Meter (volumetric) |
| Capacity between regens | From disc selection chart for your hardness level |

> **Brine draw time calculation:** If your bucket test shows 1.5 litres/min draw rate and you need 246 litres total, set brine draw time to ~164 minutes (÷ by two tanks regenerating alternately = ~82 minutes each, depending on your system cycle structure).

---

## Step 4: Plumbing

The WS1TT connects with standard 1" or 1¼" fittings. The Kinetico system used 1¼" custom adapters (E-clip style) — you will need to adapt to standard threaded or compression fittings to suit your plumbing.

Connection mapping:

| Kinetico port | Clack WS1TT equivalent |
|---|---|
| Untreated water inlet | Inlet port |
| Treated water outlet | Outlet port |
| 2nd tank connection ports | In/Out Head connections |
| Brine line (0.375" tube) | Brine line fitting (adapt as needed) |
| Drain (0.5" tube) | Drain fitting + DLFC |

---

## Step 5: Commission and Verify

1. **Restore water supply** slowly and check for leaks
2. **Manually initiate a regeneration cycle** from the controller
3. During brine draw, **time the draw** and compare to your benchmark
4. Check drain flow during backwash — should match ~3.0 GPM (11.4 L/min)
5. After first regeneration, **test outlet water hardness** to confirm resin is fully regenerated
6. Monitor for 2–3 regen cycles and adjust brine draw time if needed

---

## Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| Hard water breakthrough | Brine draw too fast / insufficient contact time | Reduce BLFC size or shorten regen interval |
| Resin not regenerating fully | Brine draw time too short | Increase brine draw time in controller |
| Excessive water to drain | Backwash time too long or DLFC too large | Reduce backwash time or swap DLFC disc |
| Bed channelling / resin in outlet | Backwash flow too high | Reduce DLFC to 2.5 GPM and re-test |
| Brine tank not refilling | BLFC blocked or wrong RFC setting | Check BLFC disc, verify refill time in controller |

---

## Notes for Swedish / Nordic Installations

- Groundwater with pump + pressure vessel (hydropress): pressure will cycle between cut-in and cut-out. The Clack venturi draw rate plateaus above ~2.75 bar so this does not affect brine draw consistency.
- Cold groundwater (5–10°C) is common. This slightly reduces brine draw rate vs. rated values but also increases hydraulic pressure on the resin bed in upflow mode — do not oversize the injector.
- Kinetico spare parts are difficult to source in Sweden. Clack parts (injectors, DLFC discs, O-ring kits, pistons) are available from multiple European water treatment suppliers and cost only a few euros each.
- The Clack WS1TT requires a **230V power supply** for the controller motor. Unlike Kinetico, it is not water-powered. Budget for a nearby power outlet if not already present.

---

## Summary Checklist

- [ ] Benchmark Kinetico brine draw rate (bucket test)
- [ ] Note venturi throat colour from spare/old head
- [ ] Order Clack WS1TT CI with upflow piston
- [ ] Order 3.0 GPM DLFC disc
- [ ] Order A (black) injector (and B/yellow as backup)
- [ ] Verify 0.40 GPM BLFC in brine valve assembly
- [ ] Install injector in UP port, plug in DN port
- [ ] Set controller to Up Brine mode
- [ ] Program brine draw time from bucket test result
- [ ] Verify first regeneration cycle and test water quality

---

*Guide developed based on Kinetico 4060 M/T / 4060s OD MAC service documentation and the Water Specialist WS1TT Drawings and Service Manual. Always consult the full Clack WS1TT CI Programming Manual for complete parameter descriptions.*

© Lennard Mooij, 2026. Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
