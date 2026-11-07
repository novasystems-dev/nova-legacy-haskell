<div align="center">

# 🏛️ Nova Legacy Haskell Bootstrap (Stage 0)

**Genesis Haskell Bootstrap Toolchain for the Nova Systems Programming Language**

<br />

[![License](https://img.shields.io/badge/license-PolyForm-a855f7?style=flat&labelColor=0f172a&logo=open-source-initiative&logoColor=white)](LICENSE)
[![Nova](https://img.shields.io/badge/language-Nova_0.3.0-38bdf8?style=flat&labelColor=0f172a&logo=rust&logoColor=white)](https://github.com/novasystems-dev/nova)
[![Stage 0](https://img.shields.io/badge/stage-0_bootstrap-10b981?style=flat&labelColor=0f172a&logo=haskell&logoColor=white)](stage0/)
[![Ecosystem](https://img.shields.io/badge/ecosystem-10%20repos-f59e0b?style=flat&labelColor=0f172a&logo=github&logoColor=white)](https://github.com/novasystems-dev)

<br />

</div>

---

## Key Pillars

1. **Deterministic Zero-GC Memory**:
   Nova employs the **Perceus reference-counting model** with compile-time in-place buffer recycling. When an object's reference count is 1, mutations execute destructively in place without allocating new memory chunks.
2. **Compile-Time Formal Verification**:
   Invariants such as non-zero division, array bounds, and arithmetic overflow bounds are proven at compile time using the **Microsoft Z3 SMT solver**.
3. **Capability-Gated Concurrency**:
   Static tracking of isolation (`iso`), immutable sharing (`val`), and thread-local references (`ref`) prevents data races and deadlocks at compile time.
4. **Bare-Metal Systems Parity**:
   Hardware raw pointers (`*mut T`, `*const T`), address-of (`&val`), dereference (`*ptr`), and inline assembly (`asm("...")`) for operating systems, hypervisors, and embedded kernels.
5. **Universal Toolchain**:
   Includes compiler (`novac`), package manager (`orbit`), interactive REPL (`nova-repl`), formatter (`nova-fmt`), linter (`nova-lint`), and language server (`nova-lsp`).

---

## Quickstart

### Installation
```bash
./install.sh
export PATH="$HOME/.local/bin:$PATH"
```

### Running an Example
```bash
novac run examples/01_hello.nova
novac run examples/08_traits_and_baremetal.nova
novac run examples/09_std_industrial.nova
```

### Interactive REPL
```bash
nova-repl
# or: novac repl
```

### Package Management with Orbit
```bash
orbit new my_project
cd my_project
orbit lock
orbit run
```

---

## Documentation
- [Language Specification](docs/spec.md)
- [Standard Library Reference](docs/stdlib.md)

---

## License
MIT License. See [LICENSE](LICENSE) for details.
