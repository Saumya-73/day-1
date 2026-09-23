# Day 2 – Agentic AI Lab Answers

## 11. Observations and Comparisons

### 11.1 ReAct Comparison

| Item | Paper Trace | Actual Agent |
|---|---|---|
| Fee lookups | 3 | 3 |
| Calculator calls | 3 | 2 |
| Total steps | 17 rows | 5 numbered steps |
| Parallel calls | No | No |
| Final answer | ₹6,750 | ₹6,750 |
| Correct? | Yes | Yes |

**Observation:**  
The actual agent used fewer calculator calls than the paper trace, but it still produced the correct final answer.

### 11.2 CoT Comparison

| Question | Without CoT | With CoT | Which was longer? |
|---|---|---|---|
| Q1 | Correct | Correct | With CoT |
| Q2 | Correct | Correct | With CoT |
| Q3 | Correct | Correct | With CoT |

**Observation:**  
All three questions were answered correctly with and without CoT. The CoT responses were longer because they showed the intermediate steps.

### 11.3 Self-Consistency

**Temperature 0.8:**
- All five runs produced the correct mathematical answer: ₹9,562.50.
- The formatting was different between runs.
- Therefore, exact-string voting gave a majority of only 1 out of 5.

**Temperature 0:**
- All five runs produced the same output.
- Majority was 5 out of 5.

**Observation:**  
Temperature 0 produced more consistent and repeatable outputs.

---

## 12. Discussion Questions

### 1. Does a different order of actions make the ReAct trace wrong?

No. The order can be different as long as the required information is obtained and the calculations are correct.

### 2. Why can CoT improve answers?

CoT asks the model to solve the problem step by step. This helps organize the calculation and can reduce mistakes.

### 3. What does ReAct provide that CoT alone does not?

ReAct can use external tools to obtain information and perform calculations. CoT alone does not automatically access external tools.

### 4. Why does self-consistency need non-zero temperature?

Non-zero temperature produces different answer variations. These can be compared and voted on. At temperature 0, repeated outputs are usually the same.

### 5. How would Plan-and-Execute differ from ReAct?

Plan-and-Execute first creates a complete plan and then executes it. ReAct interleaves reasoning, actions, and observations.

---

## 13. Additional Questions

No additional task/questions.

---

## 14. Viva Questions

### 1. What are Thought, Action and Observation in ReAct?

- Thought – decides what to do next.
- Action – calls a tool.
- Observation – receives the tool result.

### 2. What is the difference between Thought and Action?

Thought is the reasoning about the next step. Action actually performs a tool call.

### 3. What is CoT?

CoT means Chain-of-Thought. It asks the model to solve a problem step by step.

### 4. Why can't CoT alone replace ReAct?

CoT does not automatically provide external tool access. ReAct can use tools to obtain information and perform operations.

### 5. Why use non-zero temperature for self-consistency?

It creates different answer samples that can be compared using voting.

### 6. Why vote on the final answer?

Different reasoning paths may use different wording, while the final answer can be compared for agreement.

### 7. What does the same step number mean in a ReAct trace?

It can indicate that independent tool calls are part of the same agent step and may be executed in parallel.

### 8. Give one advantage and one disadvantage of CoT.

Advantage: It can help with multi-step reasoning.

Disadvantage: It produces longer responses and uses more tokens.

---

## 15. Result

ReAct successfully combined reasoning with tool use, CoT produced detailed step-by-step solutions, and self-consistency produced the correct answer repeatedly. Temperature 0 produced identical outputs across all five runs.