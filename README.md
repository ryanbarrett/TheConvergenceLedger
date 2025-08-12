# The Convergence Ledger™

**“Every Object. Every Person. Every Transaction. One Network.”**

---

## 1 ▪ Core Concept

The Convergence Ledger is a decentralized, real‑time value network where every entity has an address and every action is a transaction.

Forget banks, middlemen, and centralized choke points — you pay the thing, and the thing responds.

---

## 2 ▪ Key Components

| Old Idea                | Cyberpunk Name     | Description |
|-------------------------|--------------------|-------------|
| Wallet / Keypair        | **NodeKey**        | A unique cryptographic identity bound to a person, company, device, or object. Root of authority for everything that identity controls. |
| Public Address          | **SpecterID**      | Long, cryptic, unforgettable. Derivable from a NodeKey (or deterministically from item metadata + salt). Used for receiving value and visualized as a CipherSig. |
| Universal Basic Income  | **Flow Dividend**  | A network‑issued income stream to verified citizen NodeKeys, paid in micro‑intervals so your balance grows in real time. |
| Ledger                  | **Axiom Mesh**     | The distributed record of transactions, identity links, splits, and reputation events. Private-by-default, public proofs when required. |
| Reputation Ledger       | **GhostMark**      | Tamper‑resistant trust index from signed history, peer attestations, delivery uptime, and dispute outcomes. |
| Payments / Channels     | **ImpulseCast**    | Instant, low‑fee micro‑payments across the mesh (channel‑based). |
| Smart Contracts         | **BindScript**     | Minimal, auditable scripts that route funds, enforce splits, escrow, subscriptions, and conditions. |

---

## 3 ▪ How It Works

1) **NodeKey → SpecterIDs**  
   - A person/company holds a **NodeKey** (root keypair).  
   - That NodeKey **mints or derives** many **SpecterIDs** for products, services, campaigns, or sub‑accounts.  
   - Deterministic option: `SpecterID = H(item_description + serial + nonce)` to keep IDs stable across reprints while avoiding collisions or metadata leaks.  

2) **Direct‑Action Payments**  
   - Send credits to a SpecterID → the bound **BindScript** triggers device actions, fulfillment, or revenue routing.  
   - Payments ride **ImpulseCast** and settle on **Axiom Mesh**.

3) **Splits & Routing with BindScript**  
   - Any SpecterID can carry a **BindScript** that splits incoming funds to one or more NodeKeys (percentages, thresholds, time locks).  
   - Splits can be **static** (fixed percentages) or **dynamic** (reputation weighted, inventory‑based, or time‑decaying).

4) **Reputation Embedded in Identity (GhostMark)**  
   - Each NodeKey accrues a **GhostMark** score from successful deliveries, dispute resolutions, and peer signatures.  
   - Higher GhostMark → faster settlement, lower fees; poor actors see degraded QoS.

5) **Infinite Identities, One Root**  
   - Your Prime NodeKey can spawn unlimited SpecterIDs or delegated child NodeKeys (with scoped permissions) for teams and devices.

---

## 4 ▪ Examples

**Example 1 — Augmentation Purchase**  
- Your new hand has a **SpecterID** printed beside it in the catalog (and as a CipherSig).  
- You pay that SpecterID. The hand’s **BindScript** routes funds:  
  - 85% → Manufacturer NodeKey  
  - 10% → Clinic/Installer NodeKey (on successful activation receipt)  
  - 5% → Local distributor NodeKey  
- On-chain confirmation → the device provisioning key is released to the clinic.

**Example 2 — Flow Dividend Split**  
- The **Flow Dividend** is paid into the **Flow Treasury SpecterID**.  
- Its **BindScript** automatically **splits equally** to all registered **Citizen NodeKeys** each epoch.  
- Blacklist/penalty clauses can temporarily escrow payouts for identities under dispute, with public proof artifacts.

---

## 5 ▪ Visual Identity

- Every SpecterID can render as a **CipherSig**: a compact, rune‑based, QR‑like glyph generated entirely in‑browser.  
- Small grids (8/12/16) with multi‑state cells (symbol + rotation + fill) keep marks tiny but information‑rich — perfect for zine layouts.

---

## 6 ▪ What You Can Change / Configure

- **Derivation mode:** Deterministic (metadata + nonce) or random (wallet‑like).  
- **BindScript templates:** fixed split, milestone escrow, subscription, pay‑to‑unlock, reputation‑weighted split.  
- **Visibility:** public SpecterID with private BindScript, or public proof of split percentages for transparency.  
- **Fee policy:** per‑hop fees on ImpulseCast, waived for high GhostMark peers.  
- **Revocation & rotation:** rotate SpecterIDs while preserving provenance via signed rebind messages.

---

## 7 ▪ Threats & Mitigations (What was missing)

- **Discovery & Authenticity:**  
  - Map human‑readable names → SpecterIDs via **signed registry entries** (DNS‑like, but on Mesh).  
  - Vendor catalogs sign item pages so SpecterIDs can be verified against the vendor NodeKey.

- **Metadata Privacy:**  
  - If you derive IDs from item descriptions, include a **salt/nonce** so observers can’t guess private metadata.

- **Loss & Recovery:**  
  - **Social recovery / multi‑sig** for Prime NodeKeys.  
  - **Hardware enclave** support for manufacturing/clinic keys with time‑locked emergency rotation.

- **Replay / Double‑Spend:**  
  - ImpulseCast channels + Mesh settlement with per‑payment nonces prevent replays.  
  - BindScript includes **idempotent order refs**.

- **Versioning:**  
  - `BindScript@vX` and `CipherSig@vY` versions embedded in headers for forward compatibility.

- **Dispute Flow:**  
  - Optional **arbiter NodeKey** with cryptographic receipts; funds locked in escrow branch until resolution.

---

## 8 ▪ Minimal Spec (Sketch)

- **NodeKey:** ed25519/secp256k1 keypair.  
- **SpecterID:** base58 of `H(pubkey || meta || nonce)`; printable alias allowed.  
- **CipherSig:** rune grid params `(grid, module, states, symset, mirror, anchors)` + seed from SpecterID.  
- **BindScript:** DAG of actions: `{split[], threshold, condition[], escrow, release, fallback}` signed by the controlling NodeKey.  
- **GhostMark:** rolling score from on‑time settlements, peer attestations, dispute outcomes (EWMA).  
- **ImpulseCast:** channel updates with HTLC‑like primitives, batched settlement to Mesh.

---

## 9 ▪ The Pitch

> “In the old world, you paid people to talk to machines.  
> In the Convergence, the machines talk to you.  
> Every implant, every drone, every cup of coffee — they know their price. You know their address.  
> No waiting, no middleman. Just send the Impulse, and it happens.”

---

## 10 ▪ Currency

The Convergence Ledger’s native unit of exchange is designed for speed, micro-transactions, and instant settlement across the **Axiom Mesh**.

| Type       | Name         | Description |
|------------|--------------|-------------|
| **Ticker** | **CVX**      | Formal three-letter symbol derived from “Convergence.” Used in ledgers, exchanges, and BindScripts. |
| **Ticker** | **IMP**      | Alternate symbol from “Impulse” in *ImpulseCast*. Common in technical documentation and channel protocols. |
| **Slang**  | **shards**   | Everyday street term for small divisible units of CVX. “That’ll be 12 shards.” |
| **Slang**  | **specters** | Gritty mesh slang tied to *SpecterID*. “Send me 20 specters and we’re good.” |
| **Slang**  | **divs**     | From *Flow Dividend*. Often used when talking about UBI payouts. |
| **Slang**  | **casts**    | Short for “ImpulseCast” — “Casting” value to someone. |
| **Slang**  | **meshbits** | Network-native micro-units, smallest measurable fragment of CVX. |

**Conversion**  
- **1 CVX** = 1,000 shards = 1,000,000 meshbits  
- Slang terms are informal and context-driven; BindScripts and formal contracts always denominate in CVX.

**Usage**  
- CVX flows across the mesh in real time, settling into **NodeKeys** via **ImpulseCast** channels.  
- BindScripts can split, lock, or route CVX automatically, enabling complex financial flows without intermediaries.

---