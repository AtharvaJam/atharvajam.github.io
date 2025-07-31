---
title: Imitation Learning on UR5 arm
summary: An end-to-end model to perform everyday tasks using Robot Manipulator
date: 2025-04-20
type: docs
math: false
tags:
  - Robot Science and Systems

image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## ✅ Project Objective

Briefly explain the goal of your project, such as:

> The objective of this project was to train a visual imitation learning agent for a robotic pouring task, and validate the performance in both simulated and real environments.

---

## 📽️ Demo Video

{{< youtube D2vj0WcvH5c >}}

---

## 📄 Download Report

[⬇️ Download Full Report (PDF)](/media/my_project_report.pdf)

---

## ⚙️ Technical Setup

### Code Snippet

```python
import pandas as pd
data = pd.read_csv("data.csv")
data.head()
```

---

### Math Expression

{{< math >}}
$$
\gamma_{n} = \frac{ \left | \left (\mathbf x_{n} - \mathbf x_{n-1} \right )^T \left [\nabla F (\mathbf x_{n}) - \nabla F (\mathbf x_{n-1}) \right ] \right |}{\left \|\nabla F(\mathbf{x}_{n}) - \nabla F(\mathbf{x}_{n-1}) \right \|^2}
$$
{{< /math >}}

---

## 🧠 Self Check (Optional)

Add spoilers to quiz yourself or readers:

```markdown
{{< spoiler text="👉 Click to view the solution" >}}
You found me 🎉
{{< /spoiler >}}
```

renders as:

{{< spoiler text="👉 Click to view the solution" >}}You found me 🎉{{< /spoiler >}}

---

## 🧾 Results & Analysis

Summarize the performance, metrics, or outcomes of your project.

> The trained policy achieved a 93% success rate in simulation and generalized well to real-world settings with minor calibration.

---

## 🖼️ Visuals

You can use inline icons or images as needed:

```markdown
{{< icon name="python" >}} Python
```

renders as:

{{< icon name="python" >}} Python


---