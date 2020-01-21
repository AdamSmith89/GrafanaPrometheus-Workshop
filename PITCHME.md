@snap[text-gold text-20]
Threat Modelling
@snapend
@snap[text-black text-italic text-04 fragment]
### *Sooner The Better, But Better Late Than Never*
@snapend

Note:
- Great quote from OWASP

---
@snap[north span-100]
### Why Threat Model
@snapend

@snap[north-west text-center fragment]
<br><br>
Fail Fast
@snapend

@snap[east fragment]
Define security requirements
<br><br><br>
@snapend

@snap[west fragment]
<br><br>
Build better products
@snapend

@snap[south-east text-center fragment]
Makes us think about Security!
<br>    
@snapend

Note:
- Any suggestions?
- SecREq: Is this necessary? Do we need to design for securing X?

---
@title[Agenda]

@snap[north span-100]
### 4 Key Questions
@snapend

@snap[midpoint text-left text-10]
@ol
- What are we building?
- What can go wrong?
- What can we do?
- How did we do?
@olend
@snapend

---
@snap[north span-100]
### When To Threat Model
@snapend

@snap[west fragment]
@fa[play fa-4x]
@snapend

@snap[midpoint fragment]
@fa[sync-alt fa-4x]
@snapend

@snap[east fragment]
@fa[flag-checkered fa-4x]
@snapend

Note:
- Part of design for new code (features/bugs)
- It should be updated as design changes (we are bad at this)
- Review at the end to ensure it still matches (we are bad at this)
- Ideally legacy system should be TM'd
  - Don't do it? Per-team decision? Architect role? TD backlog? Team smash it in a day or two?
- Look at it like TDD, write test-cases first (find threats first to create tests)
- Said before, fail fast!

---

@snap[north span-100]
### Key Takeaways
@snapend

@ul
- 4 Key Questions
- Trust Boundaries
- STRIDE
- Keep it up-to-date
@ulend

Note:
- Remember at least this!
- Can anyone remember the questions?
- Can anyone remember STRIDE?
- Something we haven't been good at!

---
@snap[midpoint]
@fa[question fa-8x]
@snapend

---
@snap[north span-100]
### Useful Resources
@snapend

- [STRIDE chart](https://www.microsoft.com/security/blog/2007/09/11/stride-chart/) from MS Blog
- [CAPEC](https://capec.mitre.org/)
- [CVSS Calculator](https://www.first.org/cvss/calculator/3.0)
- Threat Modeling by Adam Shostack

Note:
- Common Attack Pattern Enumeration and Classification
  - Comprehensive dictionary of known attack patterns