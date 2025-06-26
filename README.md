# FIT5226 Assignment – Multi-Agent Dueling Deep Q-Learning in GridWorld

**Author:** Prakrit Dayal  
**Unit:** FIT5226 – Advanced Topics in AI  
**Semester:** Semester 1, 2025  
**Submission:** Individual Assignment  

---

## 🧠 Problem Overview

This project addresses a multi-agent coordination problem in a 5×5 GridWorld. **Four agents** must continuously shuttle between two locations (A and B), learning through experience to:
- Deliver items efficiently
- Avoid **head-on collisions**
- Learn optimal policies under limited observability and time pressure

The task is **non-episodic** and requires agents to learn **lifelong delivery behaviour** under defined constraints.

---

## ⚙️ Methodology

- **Learning method:** Dueling Deep Q-Network (Dueling DQN)
- **Architecture:**
  - Shared neural network across agents
  - Separate streams for state-value and advantage
- **Replay buffer:** Used for stabilised learning
- **Target network updates:** Periodic, with soft update mechanism

- **Environment design:**
  - 5x5 GridWorld
  - Shared drop-off (B) and pickup (A) points
  - Automatic pickup/drop-off when arriving at correct cell
  - No wait action allowed

- **Rewards:**
  - +25 for pickup at A
  - +55 for dropoff at B
  - −1600 for head-on collision
  - −0.1 per step
  - −2 for hitting walls

- **Options used:**
  - **Occupancy sensor for agents of opposite type** (Cost: 3)
  - **Central clock for agent update ordering** (Cost: 1)

🛒 **Total option cost:** 4 points

---

## 📊 Final Performance

| Metric                                  | Result                   |
|-----------------------------------------|---------------------------|
| ⏱️ Total training time                   | 7 min 15 sec              |
| 📉 Total collisions during training      | 1235                      |
| 🎯 Post-training accuracy                | 37496 / 38400 episodes    |
| ✅ % Solved under 20 steps               | **97.6%**                 |
| 🚀 Collision rate                        | ~0.09 per 1,000 steps     |
| 🎓 Performance points claimed            | **2** (meets top threshold)

The results satisfy all criteria for the top performance tier in the rubric.

---

## 📈 Visualisation & Evaluation

The notebook includes:
- Accuracy trend across episodes (% BAB cycles solved under 20 steps)
- Total collision monitoring
- Animated rollout of trained agents
- Final Q-values and state visualisations
- Performance summary based on assignment metrics

---

## 📁 File Structure

| File                                  | Description                                      |
|--------------------------------------|--------------------------------------------------|
| `FIT5226assignment1_32463413.ipynb`  | Complete notebook with all code, plots, and text |

No external `.py` files or data dependencies are needed.

---

## 🔧 How to Run

To view or rerun:
1. Clone the repository
2. Open `FIT5226assignment1_32463413.ipynb` in Jupyter Lab or classic Jupyter Notebook
3. Run all cells to reproduce training and visualisation

---

## 📘 Academic Context

This project was completed as part of the FIT5226 assignment at Monash University. It explores the use of Dueling DQN in a multi-agent coordination setting, incorporating reward shaping, visual diagnostics, and option-based environment design.

All work is individual and compliant with Monash's academic integrity guidelines.

---

## 📌 Acknowledgement

Generative AI was used solely for draft phrasing and formatting suggestions. All code, design, and implementation were developed, tested, and understood independently.

---
