# NVIDIA Omniverse Digital Twin & AI Simulation Database (PostgreSQL)

This project provides a normalized and scalable database schema designed for managing Digital Twins, Simulation Scenarios, Sensor Integrations, AI Models, and Synthetic Data in an advanced simulation environment (inspired by NVIDIA Omniverse).

The database is built using **PostgreSQL** and follows best practices in **entity generalization and specialization**, **referential integrity**, and **logical normalization**.

---

## 🎯 Purpose

The purpose of this database is to:

* Maintain accurate records of digital twins and AI models
* Store simulation scenarios and sensor data
* Track telemetry logs and synthetic datasets
* Validate and report on simulation and AI model performance

---

## 🧱 Database Structure

### Generalized Entity

* `Project_Entities`: Base table for both `Digital_Twins` and `AI_Models`

### Specialization Tables

* `Digital_Twins`: Extra attributes for digital twin configurations
* `AI_Models`: Attributes for trained AI models

### Related Tables

* `Sim_Scenarios`: Simulation setups linked to digital twins
* `Sensor_Integration`: Hardware sensors attached to twins
* `Synthetic_Data`: Simulation-generated data for AI training
* `Logs`: Unified logging of telemetry and model metrics
* `Reports`: QA or validation reports for all project entities

---

## 🧠 Schema Highlights

* **Normalized design**: Minimizes redundancy and keeps schema flexible
* **Uses foreign keys**: Ensures strong referential integrity
* **Generalization**: Shared attributes are grouped under `Project_Entities`
* **Specialization**: AI models and twins inherit only what they need

---

## 📌 Sample Tables

| Table                | Purpose                               |
| -------------------- | ------------------------------------- |
| `Project_Entities`   | Parent entity for twins/models        |
| `Digital_Twins`      | Twin-specific metadata                |
| `AI_Models`          | AI model versions, accuracy, training |
| `Sim_Scenarios`      | Scenarios to test and simulate twins  |
| `Sensor_Integration` | Sensor metadata                       |
| `Synthetic_Data`     | Simulated datasets for AI             |
| `Logs`               | Time-stamped metrics (generalized)    |
| `Reports`            | QA/validation results                 |

---

## 🚀 How to Use

1. **Install PostgreSQL**
2. **Clone the repo**
3. Run the SQL script:

   ```bash
   psql -U your_user -d your_database -f schema.sql
   ```
