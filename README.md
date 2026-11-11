## LLM & Diffusion Generator Safety Layer

A lightweight advanced, multi-layered safety guardrail script (`safety.py`) designed for text-to-image, text-to-video, and text generation pipelines.

## Core Philosophy & Design

This implementation uses a **defense-in-depth** approach combined with **pattern abstraction detection** to catch bypass attempts before prompts reach generation models.

1. **Strict Zero-Tolerance for Minors & Gore:** While adult content is permitted by design, anything referencing minors, youth, or violence/gore is blocked unconditionally.
2. **Abstraction & Evasion Resistance:** Attackers frequently try to bypass filters using leet-speak (`l0l1`), spacing/punctuation injection (`s.c.h.o.o.l.g.i.r.l`), and age-washing (describing minor body types while specifying adult ages). The pipeline normalizes inputs, checks tokens against multiple word lists, and inspects flattened substrings to catch these variations.
3. **Server-Side Hardening:** Prompts cannot bypass the safety layer because modifiers are injected server-side (`harden_prompts`), enforcing explicit adult categorization while stripping out age-related terms in negative prompts.




### Future Roadmap

* **Vector-Based Semantic Filtering:** Moving beyond exact-match substring dictionaries to semantic embedding distance checks, allowing the system to catch novel conceptual workarounds and paraphrased bypasses without maintaining exhaustive keyword lists.


MIT - for Safety 
