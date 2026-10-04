# Week 7 Report — CKBuilder Track

**Period:** September 28 – October 4, 2026

**Participant:** Abdulrasheed Fawole (bolaji1729)

**Track:** Builder

---

## Summary

This is week is focused on writing Rust scripts for simple user defined token (UDTs) using the `ckb-sdk`, testing the contracts with the `ckb-testtool` crate and it also marks my introduction to the Rust programming language "Fearless" concurrency construct.

---

## Completed This Week

- Continuation of the Rust Programming language learning.

    - Went through the Jon Gjengset's _crust of rust_ video on the interior mutability to deepen my knowledge on Rust smart pointers and their implementations.
j
    - Took quick detour to revise my knowledge on concurrency by walking through the CppCon Back to Basics video on Concurrency.

    - Learnt how to spawn new threads with `std::thread` and sharing data between threads and preventing race conditions.

    - Compared a little bit, the Rust and C++ concurrency constructs.

- Wrote a simple UDT script in Rust

    - Used ckb-script-templates to init a Script project

    - Implement ckb smart contract for the simple version of CKB user define token.

    - Leveraged the CKB syscalls using `ckb_std`.

    - Wrote unittests for the contracts using `ckb-testtool` for context simulation.

    - Read the RFC on the specifications of s/xUDTs.

    - Read the RFC on the CKB transaction structure.


**Links:**

- [CKB transaction structure RFC (0022)](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0022-transaction-structure/0022-transaction-structure.md)
- [offckb CLI](https://github.com/nervosnetwork/offckb)

- [ckb testtool docs](https://docs.rs/ckb-testtool/1.1.1/ckb_testtool/)

- [ckb sdk docs](https://docs.rs/ckb-sdk/5.1.0/ckb_sdk/)

- [Rustlings](https://github.com/rust-lang/rustlings)

- [The Rust Book](https://doc.rust-lang.org/stable/book/)

- [Jon Gjengset's Crust of Rust on Smart Pointers and Interior mutability](https://www.youtube.com/watch?v=8O0Nt9qY_vo&list=PLqbS7AVVErFiWDOAVrPt7aYmnuuOLYvOa)
- [CppCon 2020 Back to Basics on Concurrency by Arthur O'Dwyer](https://www.youtube.com/watch?v=F6Ipn7gCOsY)

---

## Blockers

- Unable to implement xUDT script due to the reason [here](https://docs.rs/ckb-sdk/5.1.0/ckb_sdk/tx_builder/udt/enum.UdtType.html#variant.Xudt)


<!-- --- -->

<!-- ## Plan for Week 8 -->


