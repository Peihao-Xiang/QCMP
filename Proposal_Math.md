顶级提案通常需要三个层次：

1️⃣ **清晰的问题形式化（Problem Formulation）**
2️⃣ **数学建模 / 理论框架（Mathematical Framework）**
3️⃣ **可证明或可分析的理论贡献（Theoretical Contributions）**

但还缺少：

* **数学问题定义**
* **理论性质**
* **可证明结论**

下面我帮你把 **QCMP（Question-Conditioned Multimodal Perception）** 提升到一个 **AI PhD proposal 级别的理论框架**。

---

# 1. Formal Problem Definition

我们首先形式化 **Question-Conditioned Multimodal Perception (QCMP)**。

## Environment

设：

* 视频流

[
V = {I_t}_{t=1}^{T}
]

其中

[
I_t \in \mathbb{R}^{H\times W\times C}
]

---

## Question

自然语言问题：

[
Q \sim p(Q)
]

例子：

* “Is there bleeding?”
* “Did a goal happen?”

---

## Answer

系统目标：

[
A = f(Q,V)
]

其中

[
A \in \mathcal{A}
]

例如：

* yes/no
* location
* count
* text

---

# 2. Bottom-Up Pipeline (Baseline)

传统 pipeline：

[
z = \phi(V)
]

其中：

[
z \in \mathbb{R}^{d}
]

是视频 embedding。

回答：

[
A = g(Q,z)
]

---

### Problem

embedding 是：

[
z = \phi(V)
]

在 **不知道 Q 的情况下计算**。

因此：

[
I(V;z) < H(V)
]

信息已经压缩。

当问题到来时：

[
I(Q;z)
]

可能不足。

---

# 3. Question-Conditioned Perception

你的方法：

先给问题。

[
Q \rightarrow \text{Perception Plan}
]

定义：

[
P = \pi(Q)
]

其中：

P 是 **Perceptual Query Plan**。

---

## Plan Definition

[
P = (T,S,\Omega,\Gamma)
]

其中：

T = targets
S = spatial scope
Ω = temporal scope
Γ = tool chain

---

## Evidence Extraction

执行 perception：

[
E = \mathcal{E}(V,P)
]

得到证据：

[
E = {e_1,...,e_n}
]

例如：

* bounding boxes
* OCR text
* event timestamps

---

## Answer

最终：

[
A = r(Q,E)
]

---

# 4. Information-Theoretic Advantage

核心理论命题：

### Bottom-up

[
z = \phi(V)
]

必须满足：

[
I(Q;z) \le I(V;z)
]

embedding 不可能保留所有任务信息。

---

### Question-conditioned

系统只提取：

[
E_Q
]

满足：

[
I(E_Q;Q) \gg I(z;Q)
]

因为 perception 被 Q 引导。

---

## Proposition 1

在固定表示维度 d 下：

**Question-conditioned perception 保留更多 task-relevant information。**

形式：

[
I(Q;E_Q) \ge I(Q;z)
]

在大多数任务分布下成立。

---

# 5. Computational Efficiency Model

定义 perception cost：

[
C = \sum_{i=1}^{n} c_i
]

其中：

[
c_i
]

是工具成本。

---

### Bottom-up

必须计算：

[
C_{BU} = C_{all}
]

---

### Question-conditioned

只执行：

[
C_{QC} = C_{relevant}
]

因此：

[
C_{QC} < C_{BU}
]

---

## Proposition 2

若：

[
|T_Q| \ll |T_{all}|
]

则：

[
E[C_{QC}] \ll E[C_{BU}]
]

---

# 6. Hallucination Model

定义 hallucination：

系统在 **缺乏证据时仍给出答案**。

---

### 定义 Evidence Sufficiency

[
S(E,Q)
]

若：

[
S(E,Q) < \tau
]

则证据不足。

---

### Bottom-up

LLM 仍回答：

[
P(A|Q,z)
]

---

### QCMP

系统允许：

```
insufficient evidence
```

---

## Proposition 3

如果系统允许：

[
A = \emptyset
]

当：

[
S(E,Q) < \tau
]

则 hallucination probability：

[
P_{hallucination}
]

严格降低。

---

# 7. Loss-Aware Agent (Agentic AI)

定义：

Loss Risk

[
R
]

---

## Loss sources

三种：

### Sampling loss

[
R_s
]

### Planning loss

[
R_p
]

### Tool error

[
R_t
]

---

## Total loss risk

[
R = R_s + R_p + R_t
]

---

## Agent Control

Agent policy：

[
\pi_a(s)
]

选择 action：

[
a \in {
expand_ROI,
increase_FPS,
call_expert,
human_review
}
]

目标：

[
\max ; Accuracy - \lambda C - \mu Latency
]

---

# 8. POMDP Formulation

整个系统可表示为：

POMDP：

[
(S,A,O,T,R)
]

---

### State

[
s_t = (E_t, B_t, R_t)
]

E_t = evidence
B_t = remaining budget
R_t = loss risk

---

### Action

[
a_t
]

* run tool
* expand window
* stop

---

### Observation

[
o_t = tool\ output
]

---

### Reward

[
R = Accuracy - \lambda C
]

---

# 9. Theoretical Research Contributions

顶级 PhD proposal 必须明确理论贡献。

你的理论贡献可以写成：

---

## Contribution 1

**Formal framework for question-conditioned perception**

提出新的 multimodal inference pipeline。

---

## Contribution 2

**Information-theoretic analysis of task-aware perception**

证明：

task-aware perception 保留更多相关信息。

---

## Contribution 3

**Budget-aware perception planning**

提出算法：

在 latency constraint 下最大化 evidence quality。

---

## Contribution 4

**Loss-aware agentic perception**

提出 agentic framework：

在线估计 information loss。

---

# 10. Revised Research Thrusts

现在 proposal 可以分为 **三个 research thrust**。

---

## Thrust 1

### Perceptual Query Planning

研究：

LLM 如何生成 perception programs。

---

## Thrust 2

### Budget-Aware Multimodal Perception

研究：

compute allocation。

---

## Thrust 3

### Loss-Aware Agentic Perception

研究：

如何主动减少 information loss。

---

# 11. Reviewer-Ready Contribution Statement

你可以在 proposal 中写：

> This research proposes a new paradigm for multimodal AI in which perception is actively controlled by questions rather than performed independently of them. By formalizing question-conditioned perception as a decision process over evidence acquisition under computational budgets, the proposed work aims to establish theoretical foundations and practical algorithms for efficient, reliable, and hallucination-resistant multimodal systems.

---
