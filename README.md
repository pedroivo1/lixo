# Resolução dos Exercícios de Lógica Matemática

## Capítulo 9

<details>
<summary>3. Regras de inferência para justificar os argumentos:</summary>

| Item | Argumento | Regra de Inferência |
|------|-----------|---------------------|
| (a) | `p → q ⟼ (p → q) ∨ ∼r` | Adição |
| (b) | `¬p ∧ (q → r) ⟼ ¬p` | Simplificação |
| (c) | `p → q, q → ∼r ⟼ p → ∼r` | Silogismo Hipotético |
| (d) | `p → (q → r), p ⟼ q → r` | Modus Ponens |
| (e) | `(q ∨ r) → ∼p, ∼∼p ⟼ ∼(q ∨ r)` | Modus Tollens |
| (f) | `p → q, r → ∼s ⟼ (p → q) ∧ (r → ∼s)` | Conjunção |
| (g) | `(p ∧ q) ∨ (∼p ∧ r), ∼(∼p ∧ r) ⟼ p ∧ q` | Silogismo Disjuntivo |
| (h) | `p → q ∨ r ⟼ p → p ∧ (q ∨ r)` | Absorção |
| (i) | `x + y = z → y + x = z, x + y = z ⟼ y + x = z` | Modus Ponens |
| (j) | `x,y ∈ R → x+y ∈ R, x+y ∉ R ⟼ x,y ∉ R` | Modus Tollens |
| (k) | `x ≠ 0, x ≠ 1 ⟼ x ≠ 0 ∧ x ≠ 1` | Conjunção |
</details>

## Capítulo 10

<details>
<summary>1. Verificação de validade:</summary>

<details>
<summary>(a) p → q, r → ∼q ⟼ r → ∼p</summary>

**Resolução**:
1. Construa a tabela-verdade com 8 linhas (2³)
2. Verifique que nas linhas onde ambas premissas são V, a conclusão também é V  
✅ **Argumento válido**
</details>

<details>
<summary>(b) p → ∼q, r → p, q ⟼ ∼r</summary>

**Resolução**:
1. Se q=V, então ∼q=F
2. Para p→∼q ser V, p deve ser F
3. Para r→p ser V com p=F, r deve ser F  
✅ **Argumento válido**
</details>
</details>

## Capítulo 11

<details>
<summary>4. Demonstração de não-validade:</summary>

<details>
<summary>(e) Atribuição que invalida:</summary>

- p=V, q=F, r=F, s=V, t=F, u=V
- Premissas: V, V, V, V
- Conclusão p→q = F  
✅ **Argumento inválido**
</details>

<details>
<summary>(f) Atribuição que invalida:</summary>

- p=V, q=V, r=F, s=F, t=V, v=F
- Premissas: V, V, V, V
- Conclusão p↔r = F  
✅ **Argumento inválido**
</details>
</details>


<details>
<summary>17. Demonstrações de Validade dos Argumentos</summary>

<details>
<summary>Argumento (a)</summary>

**Premissas:**
1. `p ∨ q → ∼r`
2. `p`
3. `s → r`

**Conclusão:** `∼s`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ q → ∼r`     |    | (P1)           |
|2| `p`              |    | (P2)           |
|3| `s → r`          |    | (P3)           |
|---|------------------|----|----------------|
|4| `p ∨ q`          | 2  | (AD)           |
|5| `∼r`             |1,4 | (MP)           |
|6| `∼s`             |3,5 | (MT)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (b)</summary>

**Premissas:**
1. `p ∧ (q ∨ r)`
2. `q ∨ r → ∼s`
3. `s ∨ t`

**Conclusão:** `t`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∧ (q ∨ r)`    |    | (P1)           |
|2| `q ∨ r → ∼s`     |    | (P2)           |
|3| `s ∨ t`          |    | (P3)           |
|---|------------------|----|----------------|
|4| `q ∨ r`          | 1  | (SIMP)         |
|5| `∼s`             |2,4 | (MP)           |
|6| `t`              |3,5 | (SD)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (c)</summary>

**Premissas:**
1. `p ∨ q → ∼r`
2. `q`
3. `s ∧ t → r`

**Conclusão:** `∼(s ∧ t)`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ q → ∼r`     |    | (P1)           |
|2| `q`              |    | (P2)           |
|3| `s ∧ t → r`      |    | (P3)           |
|---|------------------|----|----------------|
|4| `p ∨ q`          | 2  | (AD)           |
|5| `∼r`             |1,4 | (MP)           |
|6| `∼(s ∧ t)`       |3,5 | (MT)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (d)</summary>

**Premissas:**
1. `p → q`
2. `∼q`
3. `∼p ∨ ∼r → s`

**Conclusão:** `s`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p → q`          |    | (P1)           |
|2| `∼q`             |    | (P2)           |
|3| `∼p ∨ ∼r → s`    |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼p`             |1,2 | (MT)           |
|5| `∼p ∨ ∼r`        | 4  | (AD)           |
|6| `s`              |3,5 | (MP)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (e)</summary>

**Premissas:**
1. `p ∨ (q ∧ r)`
2. `q → s`
3. `r → t`
4. `s ∧ t → p ∨ r`
5. `∼p`

**Conclusão:** `r`

**Prova:**
|   | Proposição       | L   | Justificativa  |
|---|------------------|-----|----------------|
|1| `p ∨ (q ∧ r)`    |     | (P1)           |
|2| `q → s`          |     | (P2)           |
|3| `r → t`          |     | (P3)           |
|4| `s ∧ t → p ∨ r`  |     | (P4)           |
|5| `∼p`             |     | (P5)           |
|---|------------------|-----|----------------|
|6| `q ∧ r`          |1,5  | (SD)           |
|7| `q`              | 6   | (SIMP)         |
|8| `r`              | 6   | (SIMP)         |
|9| `s`              |2,7  | (MP)           |
|10| `t`             |3,8  | (MP)           |
|11| `s ∧ t`         |9,10 | (CONJ)         |
|12| `p ∨ r`         |4,11 | (MP)           |
|13| `r`             |5,12 | (SD)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (f)</summary>

**Premissas:**
1. `q ∨ (r → t)`
2. `q → s`
3. `∼s → (t → p)`
4. `∼s`

**Conclusão:** `r → p`

**Prova:**
|   | Proposição       | L   | Justificativa  |
|---|------------------|-----|----------------|
|1| `q ∨ (r → t)`    |     | (P1)           |
|2| `q → s`          |     | (P2)           |
|3| `∼s → (t → p)`   |     | (P3)           |
|4| `∼s`             |     | (P4)           |
|---|------------------|-----|----------------|
|5| `t → p`          |3,4  | (MP)           |
|6| `∼q`             |2,4  | (MT)           |
|7| `r → t`          |1,6  | (SD)           |
|8| `r → p`          |5,7  | (SH)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (g)</summary>

**Premissas:**
1. `p ∨ q → (p → s ∧ t)`
2. `p ∧ r`

**Conclusão:** `t ∨ u`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ q → (p → s ∧ t)` | | (P1)        |
|2| `p ∧ r`          |     | (P2)           |
|---|------------------|----|----------------|
|3| `p`              | 2   | (SIMP)         |
|4| `p ∨ q`          | 3   | (AD)           |
|5| `p → s ∧ t`      |1,4  | (MP)           |
|6| `s ∧ t`          |3,5  | (MP)           |
|7| `t`              | 6   | (SIMP)         |
|8| `t ∨ u`          | 7   | (AD)           |

✅ **Argumento válido**
</details>
</details>


## Capítulo 12:

<details>
<summary>3. Demonstrações de Validade</summary>

<details>
<summary>Argumento (a)</summary>

**Premissas:**
1. `r → (p ∧ q)`
2. `∼p ∨ ∼q`
3. `r ∨ s`

**Conclusão:** `s`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `r → (p ∧ q)`    |    | (P1)           |
|2| `∼p ∨ ∼q`        |    | (P2)           |
|3| `r ∨ s`          |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼(p ∧ q)`       | 2  | (DM)          |
|5| `∼r`             |1,4 | (MT)           |
|6| `s`              |3,5 | (SD)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (b)</summary>

**Premissas:**
1. `p ∨ q → r`
2. `∼r`
3. `∼p → s`

**Conclusão:** `s`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ q → r`      |    | (P1)           |
|2| `∼r`             |    | (P2)           |
|3| `∼p → s`         |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼(p ∨ q)`       |1,2 | (MT)           |
|5| `∼p ∧ ∼q`        | 4  | (DM)          |
|6| `∼p`             | 5  | (SIMP)         |
|7| `s`              |3,6 | (MP)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (c)</summary>

**Premissas:**
1. `(p → q) → r`
2. `∼r`
3. `(∼p ∨ q) ∨ s`

**Conclusão:** `s`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `(p → q) → r`    |    | (P1)           |
|2| `∼r`             |    | (P2)           |
|3| `(∼p ∨ q) ∨ s`   |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼(p → q)`       |1,2 | (MT)           |
|5| `p ∧ ∼q`         | 4  | (NEG→)         |
|6| `∼(∼p ∨ q)`      | 5  | (DM)          |
|7| `s`              |3,6 | (SD)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (d)</summary>

**Premissas:**
1. `∼(p ∧ q) → (r → s)`
2. `r ∧ ∼s`
3. `q → t`

**Conclusão:** `t`

**Prova:**
|   | Proposição       | L   | Justificativa |
|---|------------------|-----|---------------|
|1| `∼(p ∧ q) → (r → s)` | | (P1)         |
|2| `r ∧ ∼s`         |     | (P2)          |
|3| `q → t`          |     | (P3)          |
|---|-----------------|-----|---------------|
|4| `~(~r ∨ s)`      |  2  | (DM)         |
|5| `∼(r → s)`       |4,5  | (COND)        |
|6| `p ∧ q`          |1,6  | (MT)          |
|7| `q`              | 7   | (SIMP)        |
|8| `t`              |3,8  | (MP)          |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (e)</summary>

**Premissas:**
1. `p ∨ ∼(q ∨ ∼r)`
2. `∼p`
3. `r → (s ∨ t)`

**Conclusão:** `s ∨ t`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ ∼(q ∨ ∼r)`  |    | (P1)           |
|2| `∼p`             |    | (P2)           |
|3| `r → (s ∨ t)`    |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼(q ∨ ∼r)`      |1,2 | (SD)           |
|5| `∼q ∧ r`         | 4  | (DM)          |
|6| `r`              | 5  | (SIMP)         |
|7| `s ∨ t`          |3,6 | (MP)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (f)</summary>

**Premissas:**
1. `p ∨ q → r`
2. `∼r`
3. `q ∨ (∼s ∨ t)`

**Conclusão:** `s → t`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ q → r`      |    | (P1)           |
|2| `∼r`             |    | (P2)           |
|3| `q ∨ (∼s ∨ t)`   |    | (P3)           |
|---|------------------|----|----------------|
|4| `∼(p ∨ q)`       |1,2 | (MT)           |
|5| `∼p ∧ ∼q`        | 4  | (DM)          |
|6| `∼q`             | 5  | (SIMP)         |
|7| `∼s ∨ t`         |3,6 | (SD)           |
|8| `s → t`          | 7  | (IMP)          |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (g)</summary>

**Premissas:**
1. `p ∨ (∼q → r)`
2. `∼(p ∨ s) ∧ ∼r`

**Conclusão:** `q`

**Prova:**
|   | Proposição       | L  | Justificativa  |
|---|------------------|----|----------------|
|1| `p ∨ (∼q → r)`   |    | (P1)           |
|2| `∼(p ∨ s) ∧ ∼r`  |    | (P2)           |
|---|------------------|----|----------------|
|3| `∼(p ∨ s)`       | 2  | (SIMP)         |
|4| `∼p ∧ ∼s`        | 3  | (DM)          |
|5| `∼p`             | 4  | (SIMP)         |
|6| `∼r`             | 2  | (SIMP)         |
|7| `∼q → r`         |1,5 | (SD)           |
|8| `q`              |6,7 | (MT)           |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (h)</summary>

**Premissas:**
1. `(p → q) → r`
2. `∼r ∨ s`
3. `∼(p ∧ ∼q)`
4. `s ∨ t → u`

**Conclusão:** `u`

**Prova:**
|   | Proposição       | L   | Justificativa |
|---|------------------|-----|---------------|
|1| `(p → q) → r`    |     | (P1)          |
|2| `∼r ∨ s`         |     | (P2)          |
|3| `∼(p ∧ ∼q)`      |     | (P3)          |
|4| `s ∨ t → u`      |     | (P4)          |
|---|------------------|-----|---------------|
|5| `p → q`          | 3   | (EQ)          |
|6| `r`              |1,5  | (MP)          |
|7| `s`              |2,6  | (SD)          |
|8| `s ∨ t`          | 7   | (AD)          |
|9| `u`              |4,8  | (MP)          |

✅ **Argumento válido**
</details>

<details>
<summary>Argumento (i)</summary>

**Premissas:**
1. `∼p ∨ q`
2. `∼s → ∼r`
3. `p ∨ (r ∧ t)`

**Conclusão:** `q ∨ s`

**Prova:**
|   | Proposição       | L   | Justificativa |
|---|------------------|-----|---------------|
|1| `∼p ∨ q`         |     | (P1)          |
|2| `∼s → ∼r`        |     | (P2)          |
|3| `p ∨ (r ∧ t)`    |     | (P3)          |
|---|------------------|-----|---------------|
|4| `r → s`          | 2   | (CP)          |
|5| Caso 1: `p`      |     | (Hip)         |
|6| `q`              |1,5  | (SD)          |
|7| `q ∨ s`          | 6   | (AD)          |
|---|------------------|-----|---------------|
|8| Caso 2: `r ∧ t`  |     | (Hip)         |
|9| `r`              | 8   | (SIMP)        |
|10| `s`             |4,9  | (MP)          |
|11| `q ∨ s`         | 10  | (AD)          |

✅ **Argumento válido**
</details>
</details>
