# MRAN — Mathematically Redefined Algorithmic Notation

MRAN is a pseudocode notation standard designed to merge mathematical formalism and programming logic. It is strict, readable, and language-agnostic — built for expressing algorithms clearly and precisely without being tied to any programming language.

Most pseudocode is either too loose to be consistent or too close to a specific language to be truly general. MRAN sits in the middle: formal enough to be unambiguous, readable enough for anyone to follow.

---

## A Quick Look

```
Algorithm to search for a target in an array

1) START
2) INPUT myArray, target
3) SET found = FALSE
4) FOR i = 0, i < myArray.length, i++ THEN:
      I) IF myArray[i] = target THEN:
            i) SET found = TRUE
            ii) OUTPUT "Found {target} at index {i}."
            iii) BREAK
5) IF found = FALSE THEN:
      I) OUTPUT "{target} not found in array."
6) STOP
```

---

## What's in MRAN

- **Strict syntax** — every construct has one defined, unambiguous form
- **SET vs COMPUTE** — semantic distinction between assignment and calculation
- **Mathematical operators** — supports `×`, `÷`, `√`, `∈`, `≤`, set builder notation, and more
- **Structured nesting** — Arabic → Roman → lowercase roman → alphabets → Greek
- **Error handling** — `TRY:` / `IF error THEN:` without a CATCH keyword
- **Optional typing** — declare types only when clarity demands it

---

## Full Specification

→ [MRAN.md](./MRAN.md)

---

## License

See [LICENSE](./LICENSE) for details.

---

*MRAN — Mathematically Redefined Algorithmic Notation*
