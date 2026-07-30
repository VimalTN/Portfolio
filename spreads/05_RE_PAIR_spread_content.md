# RE:PAIR — Spread Content (single A3 sheet)

Perception-Driven Closed-Loop Robotic Repair · Hardware II seminar
MRAC / MaAI collaboration

---

## SINGLE SHEET

**Title:** RE:PAIR
**Subtitle:** Perception-driven, decision-visible closed-loop robotic repair

**Meta line:**
IAAC · Hardware II · 2026 — Vimal TN, Onur Berk Doğrultucu, Nithik Vairamuthu, Arthur Rotstein, Sam Holcombe (MRAC / MaAI)

**Hypothesis / hook (pull-quote):**
"If a robot can see a crack, plan the fix, and check its own work — repair becomes a closed loop, not a human errand."

**Problem (~30 words):**
Building repair is reactive and manual — cracks are found by eye, judged by guesswork, and fixed without record. RE:PAIR closes the loop: detect, repair, verify, autonomously.

**The loop (4 step labels for a diagram):**
DETECT — YOLOv8 segmentation finds and masks cracks, extracts a centreline
PLAN — the mask becomes a robotic toolpath
REPAIR — a UR10 arm 3D-prints into the crack (superficial or structural)
VERIFY — the system re-scans and confirms the result

**System (~30 words):**
Built on ROS2 with a UR10 arm and RViz. A state machine drives the pipeline; every decision is made visible — perception, planning, and failure causes surfaced live, so the robot stops behaving like a black box.

**The real lesson (~35 words) — the differentiator, keep it:**
The hard part wasn't the model — it was integration. A 180° base-yaw mismatch breaks inverse kinematics; a lost camera halts the pipeline; a wrong coordinate frame turns correct code into wrong motion. Integration is a discipline, not a bug.

**Stats strip:**
YOLOv8 nano-seg · mAP50 0.514 · 46.6 ms/image · ROS2 + UR10

**Closing quote:**
"We made the robot's reasoning visible — because a repair you can't inspect is a repair you can't trust."

**Footer:** Repairman Stack v1.0 · ROS2 · UR10 · YOLOv8 · Flask bridge to Rhino/Grasshopper

---

## IMAGES

Single sheet: UR10 arm repairing on the wall (hero) + the 4-step detect→verify strip
+ YOLO segmentation output (input / mask / centreline) + RViz observability screen

## WEBSITE CARD (short)

**RE:PAIR** — 2026 · Hardware II
A perception-driven, closed-loop robotic repair system. A YOLOv8 model detects and
masks structural cracks; a UR10 arm 3D-prints the repair and re-scans to verify — with
every decision surfaced live in a ROS2 observability interface. Robots that mend, and
show their work.
Tags: Computer Vision · ROS2 · Robotic Fabrication · YOLOv8
Links: LinkedIn ⚠️ · GitHub ⚠️

---

⚠️ Needed: your role, GitHub/LinkedIn link, hero photo of the robot in action.
