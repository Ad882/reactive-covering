<h1 align='center'> Reactive Coverage of a Large Area with a Satellite Constellation 🛰️ </h1>

## **🌍 Context and Objectives:**
- A constellation of **32 low Earth orbit satellites** is used to monitor **Areas of Interest (AOIs)** on a large scale (countries, regions).  
- Applications include: **forest fire monitoring, flood observation, illicit activity detection, conflicts**, and more.  

The user aims to:  
  - 🗺️ Collect data in response to unexpected events within their area of interest.  
  - 🎯 Reserve satellite passages **in advance** to avoid conflicts with other users.  
  - ⏱️ For each sliding window of reactivity duration (2, 4, or 12 hours), select at least one satellite passage covering one of the AOI's accesses.

<br>

## **📥 Input Data:**
The input data is stored in the [data](data) folder:  

1. **Areas of Interest (AOIs):**  
   - Geographic characteristics (coordinates, visibility windows).  
   - List of possible accesses for each satellite (date and duration of passage).  

2. **Reactivity Objectives:**  
   - Ensure deadlines (12h, 4h, 2h) are respected to cover at least one access within a given window.  
   - Three `.json` files in [data](data), each corresponding to one of the reactivity constraints.  

3. **Observation Requests:**  
   - A request is fulfilled if at least one access is covered during a satellite passage (minimum duration: **30 seconds**).  

<br>

## **🚀 Optimization Problem:**
- **Decisions to Make:**  
  - Select which satellite passages to reserve.  
  - Define the start and end intervals for each reservation.  

- **Constraints:**  
  - Only one reservation per passage.  

- **Criteria to Optimize:**  
  - **Minimize costs** for the user (fixed fees + cost per unit of reserved time).  
  - **Maximize satisfaction** of observation requests.  

<br>

## **🛠️ Project Approach:**

1. **Step 1: Familiarization:**  
   - Analyze the provided data.  
   - Define metrics to evaluate solutions (e.g., total cost, request satisfaction).  

2. **Step 2: Optimization with Full Passages:**  
   - Test a **MILP approach** using DOCPLEX.  
   - Explore heuristic methods (greedy algorithms, metaheuristics).  

3. **Step 3: Optimization with Partial Passages:**  
   - Select only specific time intervals within passages to reduce costs for the user.  

4. **Step 4: Multi-Criteria Problem:**  
   - Perform Pareto analysis (**cost vs satisfaction**).  
   - Generate optimal solutions based on multiple criteria.  

This project provides the opportunity to explore the entire optimization pipeline, from data formalization to solution visualization.

<br>

---

## **📋 Requirements:**
To run the provided Python code, you need:  
- **Python 3.8+**  
- Required libraries (install using `pip install -r requirements.txt`):  
  - `matplotlib`  
  - `numpy`  
  - `docplex`   
    ⚠️ DOcplex (IBM Decision Optimization CPLEX Modeling for Python) requires a license, as it is based on the use of IBM CPLEX Optimizer, a commercial product. 
  - `cartopy`  

<br>

## **📖 Learn More:**
For more details, check the [documentation](Documentation.pdf).  

<br>

## **ℹ️ Additional Notes:**
- The **final project report is in French** 🇫🇷.  
- This README serves as an overview of the work and deliverables in English.  
