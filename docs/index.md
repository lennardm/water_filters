# Swapping a Kinetico Valve Controller for a Clack WS1TT

## A practical guide for Kinetico 4060 M/T, 4060s OD MAC and similar twin-tank systems

---

## Background & Why This Guide Exists

Kinetico water treatment systems are well-engineered and long-lasting — but their valve heads are proprietary, expensive (€400–1000+), and difficult to source in Sweden/Europe as spare parts. When the valve controller fails, many owners are told to replace the entire system. Maintenance kits can be found on eBay, but these might not be made for the valve controllers of the 4060 system, which has two more spring loaded valves. These spring loaded valves are one issue that caused a failed rinse after the backwash in our system, resulting in salt water coming into the house each time a regeneration was done. Becuase of this, and because the filter itself was properly filtering the water (other than the salt water), I decided to change the Kinetico valve head to a **Clack WS1TT**.

This guide explains how to replace the Kinetico valve head with a **Clack WS1TT**, an industry-standard twin-tank control valve that is widely available, fully documented, and inexpensive to service. The Clack WS1TT can replicate all regeneration functions including countercurrent (upflow) regeneration. However, **downflow regeneration is the more commonly available configuration** and works well in practice with only a modest reduction in salt efficiency. 

> ⚠️ This guide was developed based on the swap on a **Kinetico 4060 M/T** (anion/cation mixed-bed resin + Macrolite upper tanks). Most principles apply to other 4060s variants. Always verify specifications for your specific model.

This guide is provided for free, and reflects what I have done to make it work. Do your own research! AI chat + searching tools like Perplexity are very useful. I can't take responsibility for the correctness of this guide, nor of any problems you may have when you are swapping yourself.

---

## Understanding Your Kinetico System

Before starting, identify your model. The main variants are:

| Model | Upper tanks | Lower tanks | Service flow | Regen flow |
|---|---|---|---|---|
| 4060s OD MAC | Macrolite (5 micron filter) | Standard cation resin | Downflow | Countercurrent (upflow) |
| 4060s OD AC | Activated carbon | Standard cation resin | Downflow | Countercurrent (upflow) |
| 4060 M/T | Macrolite | Anion/cation mixed resin | Downflow | Countercurrent (upflow) |
| 4040s OD | Fine mesh cation resin | Activated carbon | Upflow | Countercurrent |

**All these models use countercurrent regeneration** — brine flows opposite to the normal service flow direction. This is more salt-efficient but requires a specific upflow valve body on the Clack side (see below).

### Key Kinetico specs (4060s OD MAC / 4060 M/T)

| Parameter | Value |
|---|---|
| Tank size (upper) | 2× 8" × 17" |
| Tank size (lower) | 2× 8" × 24" |
| Backwash flow control | 3.00 GPM (4060s OD MAC) |
| Brine refill flow control | 0.40 GPM |
| Salt dose per regen | ~4.4 lbs / ~2.0 kg (countercurrent optimised) |
| Regen volume | 65 gallons / 246 litres |
| Regen time | 40 minutes |
| Venturi throat (OD MAC) | Orange, part 10060 |
| Venturi throat (M/T) | Likely white — confirm on your unit |

---

## Upflow vs Downflow Regeneration — Important Decision

> ⚠️ **Check your specific Clack manual regarding field conversion between upflow and downflow.**
> Some valve models are not convertible; others are. With the WS1TT CI (as of the 2013 manual,
> page 22), field conversion **is** possible as long as the software supports Up Brine. To convert
> to upflow you need to: swap in the upflow piston (V3011-01), move the injector to the UP port,
> plug the DN port, and set the controller to Up Brine. A mismatch of piston and software setting
> will result in hard water bypass during service.

| | Upflow (countercurrent) | Downflow (co-current) |
|---|---|---|
| Matches Kinetico regen direction | ✅ Yes | ❌ No |
| Salt efficiency | Higher (~4.4 lbs/regen) | Lower (~5–5.5 lbs/regen) |
| Main piston | Black/amber two-tone, V3011-01 | Solid amber, V3011 |
| Injector port | UP port | DN port |
| Injector (8" tank) | A (black) | C (violet) |
| Controller setting | Up Brine | Dn Brine |
| Availability | Less common — verify with supplier | Standard — widely available |

**Practical recommendation:** If you can source the upflow valve body, use it. If not, downflow works well and is the pragmatic choice — the salt efficiency difference is ~20–30% more salt per regen, which is acceptable for most home installations.

---

## Tools & Parts Required

### Clack WS1TT parts to order

- **Clack WS1TT CI control valve** — specify **upflow or downflow** body at time of order (CI controller supports both via Up Brine / Dn Brine setting)
- **DLFC (Drain Line Flow Control) disc: 3.0 GPM** — matches Kinetico backwash spec
- **Injector:**
  - Upflow: **A (black)** for 8" tanks
  - Downflow: **C (violet)** for 8" tanks
  - Have the next size available as backup
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
6. Note: above ~40 PSI (2.75 bar) the venturi draw rate plateaus, so exact pressure is not critical for this test

> **Why this matters:** The Clack injector controls brine draw rate. If you choose an injector that draws too fast for anion/cation resin, regeneration will be incomplete. Matching the Kinetico rate gives you a proven starting point.

Also note the **venturi throat colour** when disassembling the Kinetico valve:
- Orange = standard cation/Macrolite variant (part 10060)
- White = smaller orifice, likely M/T or similar variant (part 1043)
- White suggests slower draw rate → confirms conservative injector sizing is correct

---

## Step 2: Identify the Correct Clack Injector

Cross-reference your measured brine draw rate (litres/min) against the Clack WS1TT injector flow rate table in the service manual.

For **8" tanks**, the WS1TT manual table recommends:

| Config | Injector | Colour | Port |
|---|---|---|---|
| Upflow regen | A | Black | UP port (plug DN) |
| Downflow regen | C | Violet | DN port (plug UP) |

**For anion/cation mixed resin (M/T model):** slower brine draw is preferable for better ion exchange contact time. Do not upsize the injector even if draw seems slow — use the BLFC to fine-tune if needed.

**Cold water note (5–10°C):** Cold water is more viscous, slightly reducing draw rate vs rated values. In upflow mode, it also increases hydraulic pressure on the resin bed — do not oversize the injector. In downflow mode this is less of a concern.

---

## Step 3: Configure the Clack WS1TT

### Physical configuration — Downflow (standard availability)

1. Verify the **solid amber downflow main piston (V3011)** is installed
2. Install **C (violet) injector** in the **DN port**
3. Install a **plug** in the UP port
4. Install the **3.0 GPM DLFC disc** in the drain line fitting
5. Install or verify the **0.40 GPM BLFC** in the brine line fitting

### Physical configuration — Upflow (if sourced)

1. Verify the **black/amber upflow main piston (V3011-01)** is installed in an **upflow valve body**
2. Install **A (black) injector** in the **UP port**
3. Install a **plug** in the DN port
4. Install the **3.0 GPM DLFC disc** in the drain line fitting
5. Install or verify the **0.40 GPM BLFC** in the brine line fitting

### Controller programming (CI controller)

Enter master programming mode and configure:

| Parameter | Downflow setting | Upflow setting |
|---|---|---|
| Brine/slow rinse cycle | **Dn Brine** | **Up Brine** |
| Backwash time | ~10 min | ~10 min |
| Brine draw time | From bucket test | From bucket test |
| Slow rinse time | 45–60 min (anion resin needs longer) | 45–60 min |
| Refill time | Target brine volume ÷ 0.40 GPM | Target brine volume ÷ 0.40 GPM |
| Salt dose | ~5–5.5 lbs / 2.3–2.5 kg | ~4.4 lbs / 2.0 kg |

> **Brine draw time:** Use your bucket test result — total minutes until brine is exhausted. Program this directly into the brine draw stage duration.

> **Slow rinse:** For anion/cation mixed resin, slow rinse after brine draw is critical. Set generously (45–60 min) to ensure full displacement of spent brine regardless of upflow or downflow configuration.

---

## Step 4: Plumbing

The WS1TT connects with standard 1" or 1¼" fittings. The Kinetico system used 1¼" custom adapters (E-clip style) — adapt to standard threaded or compression fittings to suit your plumbing.

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
3. During brine draw, **time the draw** and compare to your Kinetico benchmark
4. Check drain flow during backwash — should match ~3.0 GPM (11.4 L/min)
5. After first regeneration, **test outlet water hardness** to confirm resin is fully regenerated
6. Monitor for 2–3 regen cycles and adjust brine draw time or salt dose if needed

---

## Troubleshooting

| Symptom | Likely cause | Fix |
|---|---|---|
| Hard water breakthrough | Insufficient brine contact time | Extend slow rinse time; check injector size |
| Resin not regenerating fully | Brine draw time too short | Increase brine draw time in controller |
| Excessive water to drain | Backwash time too long or DLFC too large | Reduce backwash time or swap DLFC to 2.5 GPM |
| Bed channelling / resin in outlet | Backwash flow too high | Reduce DLFC to 2.5 GPM and re-test |
| Brine tank not refilling | BLFC blocked or wrong refill time | Check BLFC disc; verify refill time in controller |
| Hard water bypass during service | Valve body/piston mismatch | Verify upflow body + upflow piston, or downflow body + downflow piston — never mix |

---

## Notes for Swedish / Nordic Installations

- Groundwater with pump + pressure vessel (hydropress): pressure cycles between cut-in and cut-out. The Clack venturi draw rate plateaus above ~2.75 bar so this does not affect brine draw consistency.
- Cold groundwater (5–10°C) slightly reduces brine draw rate vs. rated values. In upflow mode, do not oversize the injector as cold dense water increases hydraulic pressure on the resin bed.
- Kinetico spare parts are difficult to source in Sweden. Clack parts (injectors, DLFC discs, O-ring kits, pistons) are available from multiple European water treatment suppliers for a few euros each.
- The Clack WS1TT requires a **230V power supply** for the controller motor. Unlike Kinetico, it is not water-powered. Ensure a nearby power outlet is available.

---

## Summary Checklist

- [ ] Identify your Kinetico model (4060 M/T, 4060s OD MAC, etc.)
- [ ] Decide: upflow or downflow regen (upflow = more efficient; downflow = easier to source)
- [ ] Benchmark Kinetico brine draw rate (bucket test)
- [ ] Note venturi throat colour from spare/old Kinetico head
- [ ] Order Clack WS1TT CI — check manual for field convertibility; if convertible, order upflow piston (V3011-01) separately if needed
- [ ] Order 3.0 GPM DLFC disc
- [ ] Order correct injector: A/black (upflow) or C/violet (downflow)
- [ ] Verify 0.40 GPM BLFC in brine valve assembly
- [ ] Install injector in correct port; plug the other port
- [ ] Set controller to Up Brine or Dn Brine to match valve body
- [ ] Program brine draw time from bucket test result
- [ ] Set slow rinse to 45–60 min (anion/mixed resin)
- [ ] Verify first regeneration cycle and test water quality

---

*Guide developed based on Kinetico 4060 M/T / 4060s OD MAC service documentation and the Water Specialist WS1TT Drawings and Service Manual. Always consult the full Clack WS1TT CI Programming Manual for complete parameter descriptions.*

*© Lennard Mooij, 2026. Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
