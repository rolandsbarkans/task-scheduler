## Priority-Based Daily Task Scheduler
 
This project asks the following question:
> Given a list of tasks with dependencies and optional fixed start times, what order should you do them in to get the most done in a day?
 
I build a custom **max-heap priority queue** from scratch and use it to power a `TaskScheduler` that assigns each task a numeric priority based on how many other tasks it unlocks and how long it takes. Fixed-time tasks get a large priority bonus so they always land get executed at the correct time. The scheduler then runs a loop: pull the highest-priority available task, schedule it, remove it as a dependency for everything else, repeat.
 
To understand how the scheduler performs as inputs grow, I define three input types (best-case, worst-case, and average-case), derive their theoretical time complexities (**O(n²)** and **O(n³)**), and verify those empirically by timing the scheduler over up to 1,000 tasks and fitting linear regression models to the rescaled runtime curves.
 
---
 
### Getting Started
 
To run the notebook and reproduce the analysis, clone the repo and follow the steps below.
 
**Prerequisites**
 
- Python 3.x
- Jupyter Notebook or JupyterLab
---
 
### Installation
 
**1. Clone the repository**
 
    git clone https://github.com/yourusername/task-scheduler.git
    cd task-scheduler
 
**2. Create and activate a virtual environment**
 
    python3 -m venv venv
    source venv/bin/activate        # On Windows: venv\Scripts\activate
 
**3. Install dependencies**
 
    pip install -r requirements.txt
 
---
 
### Usage
 
Launch the Jupyter Notebook to see the full pipeline:
 
    jupyter notebook task_scheduler.ipynb