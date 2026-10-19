# Week 9 Report — CKBuilder Track

**Period:** October 12 – October 18, 2026

**Participant:** Abdulrasheed Fawole (bolaji1729)

**Track:** Builder

---

## Summary

The highlight of this week is starting a project for a custom lock script. I write a custom voluntary charity donation vault (zakat-vault) locks script.

---

## Completed This Week

- Re-read the nervos doc on the rust minimal script example

- Project scaffolding
    - Generated a new project scaffold using the `cargo generate` command.

    - Used the generated makefile to add new lockscript contract rust crate to the project.

- Writing Script

    - The script is configured through 66 bytes of scripts args
        - `owner_lock_hash` 32byte for who may withdraw
        - `charity_lock_script` 32bytes
        - `rate_bps` 2bytes for basis point rate
    
    - Implemented owner authrosation, withdrawal and sharing.


**Links:**

- [zakat-vault](https://github.com/Abdulrasheed1729/zakat-vault)

- [CKB transaction structure RFC (0022)](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0022-transaction-structure/0022-transaction-structure.md)

- [Simple Lock doc tutorial](https://docs.nervos.org/docs/script/rust/rust-example-simple-lock)

- [ckb sdk docs](https://docs.rs/ckb-sdk/5.1.0/ckb_sdk/)

- [Minimal lock script example](https://docs.nervos.org/docs/script/rust/rust-example-minimal-script)


---

## Blockers

- Couldn't test the contract because I was trying to grok the example tests from the minimal script example

---

## Plan for Week 10

- Test the contract


