# Week 10 Report — CKBuilder Track

**Period:** October 19 – October 25, 2026

**Participant:** Abdulrasheed Fawole (bolaji1729)

**Track:** Builder

---

## Summary

The highlight of this week is fixing the broken test suite from last week, then pivoting the project from a zakat-vault to a **sadaqah-vault** — a voluntary-giving lock script instead of one modeling zakat's rigid nisab/hawl/rate rules.
Redesigned and reimplemented the contract to support multiple owner-approved charities instead of a single fixed one.

---

## Completed This Week

- Contract review and audit
    - Did a full pass over the existing lock script, args layout, owner-authorization logic, and withdrawal/charity-share math.


- Decided to drop "zakat" framing for "sadaqah"
    - Zakat has fixed rules (2.5% rate, nisab threshold, hawl holding period, 8 fixed recipient categories/asnaf) that don't map cleanly onto an on-chain contract without making uncomfortable religious-compliance claims.

    - Reframed the contract as a self-imposed giving commitment: *"whenever I withdraw, at least X% goes to charity I've pre-approved"* — voluntary, flexible rate, flexible recipients, no time/threshold constraints — which is a much better fit for what the contract can actually enforce on-chain.

- Redesigned charity recipient flexibility
    - Went from a single hardcoded charity lock hash to a small owner-approved list (up to 4 charities), with the required donation share payable as a split across any subset of the approved set.

    - Re-encoded script args as `owner_lock_hash(32) | rate_bps(2) | charity_count(1) | charity_lock_hash[1..=4](32 each)`.

    - Added dedicated error variants (`BadCharityCount`, `DuplicateCharity`, `MathOverflow`) instead of overloading unrelated error codes.

    - Added an `enable_log` feature gating debug logging of computed `withdrawn` / `required` / `paid` values.

- Expanded test coverage
    - Grew the test harness into a `CaseParams` struct so new scenarios are cheap to add.

    - 12 tests total now, including splitting a withdrawal's share across two approved charities, verifying payments to a non-approved lock don't count, duplicate-charity rejection, and charity-count bounds (0 and >4).


**Links:**

- [sadaqah-vault](https://github.com/Abdulrasheed1729/zakat-vault)

- [CKB transaction structure RFC (0022)](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0022-transaction-structure/0022-transaction-structure.md)

- [ckb-std source](https://github.com/nervosnetwork/ckb-std)

- [ckb-testtool](https://github.com/nervosnetwork/ckb-testtool)

---

## Blockers

None this week.

---

## Plan for Week 11

- Explore whether sUDT/token support is worth adding, beyond pure CKByte capacity.
