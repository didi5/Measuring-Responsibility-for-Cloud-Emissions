# Measuring-Responsibility-for-Cloud-Emissions
Query-level carbon attribution model for sustainable data management, enabling peak-aware and fair CO₂ responsibility in cloud database systems.


# Fair-CO₂ Query-Level Carbon Attribution

**From Peak Awareness to Carbon-Aware Optimization**

A framework for attributing cloud carbon emissions at the individual query level, enabling databases to make carbon-aware execution decisions.

---

## 🎯 The Problem

All major cloud providers are missing their carbon reduction targets. Why? **Efficiency gains just enable MORE computing, not greener computing.**

Current carbon accounting operates at the workload level, hiding which specific queries waste energy. **We can't optimize what we can't measure.**

---

## 💡 The Solution

This project extends the Fair-CO₂ framework from tenant-level to **query-level carbon attribution**, enabling:

1. **Fair Attribution** - Account for base power, peak demand, and shared infrastructure
2. **Query-Level Visibility** - Each query gets its own carbon price
3. **Carbon-Aware Optimization** - Databases choose execution strategies based on carbon intensity

---

## 🔬 Research Foundation

**Based on lectures from Hasso Plattner Institute:**
- **Tilmann Rabl**: Sustainable Data Management - Hardware efficiency plateau (only 1.45x improvement over 10 years)
- **Andreas Kipf**: Workload-Driven Optimizations - Predicate caching reduces scanned rows by 4x

---

## 🚀 How It Works

### Phase 1: Multi-Dimensional Peak-Aware Management
Fair attribution accounting for peak demand and shared infrastructure. Better utilization reduces both operational and embodied carbon.

### Phase 2: Query-Level Extension
Maps per-query resource usage (CPU, memory, I/O) to time-aware carbon intensity signals from the grid.

**Example:**
```python
Query A: SELECT * FROM orders WHERE date > '2024-01-01'
→ Resource usage: 1000 CPU-seconds, 500 MB memory
→ Grid intensity: 400g CO₂/kWh (peak hours)
→ Carbon cost: 5.2 kg CO₂

Query B: Same query, but uses cached predicate
→ Resource usage: 250 CPU-seconds, 100 MB memory  
→ Grid intensity: 400g CO₂/kWh
→ Carbon cost: 1.3 kg CO₂ (75% savings!)
```

### Phase 3: Carbon-Aware Query Optimization
The optimizer selects execution strategies that balance performance and emissions:
- **High carbon intensity** → Use predicate cache, materialized views
- **Low carbon intensity** → Scan fresh data, rebuild indexes

---

## 📊 Key Results

- **4x fewer rows scanned** using predicate caching (Kipf, 2025)
- **0.5% overhead** for caching mechanism
- **75% carbon reduction** for cached queries vs. full table scans
- **Enables carbon budgets** per user/team to counter Jevons Paradox

---


## 🌍 Impact

**Addresses three dimensions:**

✅ **Carbon-Aware Optimization** - Software-level efficiency mechanisms as "energy equivalents"

✅ **Granular Visibility** - Developers see carbon costs in real-time

✅ **Fair Accountability** - Individual carbon budgets enable absolute caps (Rabl's solution to Jevons Paradox)

---

## 📚 Research Questions

1. How can AI automatically identify "energy equivalents" for common query patterns during peak carbon intensity?
2. How to visualize carbon trade-offs to developers (e.g., materialized view vs. raw query)?
3. How does predicate caching reduce carbon responsibility attributed to specific users?

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────┐
│          Database Query Execution           │
└──────────────────┬──────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────┐
│      Query Resource Usage Profiling         │
│   (CPU, Memory, I/O from pg_stat_statements)│
└──────────────────┬──────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────┐
│     Grid Carbon Intensity (API Fetch)       │
│      (ElectricityMaps, WattTime, etc.)      │
└──────────────────┬──────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────┐
│   Carbon Attribution (Fair-CO₂ Extension)   │
│   Carbon = Usage × PowerModel × Intensity   │
└──────────────────┬──────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────┐
│    Carbon-Aware Query Optimizer             │
│  • Predicate caching                        │
│  • Materialized views                       │
│  • Temporal shifting                        │
│  • Index vs. sequential scan                │
└─────────────────────────────────────────────┘
```

---

## 🛠️ Installation

```bash
git clone https://github.com/yourusername/query-carbon-attribution.git
cd query-carbon-attribution
pip install -r requirements.txt
```

---

## 📖 Documentation

See the `docs/` folder for:
- Detailed methodology
- API reference
- Integration guides for PostgreSQL, MySQL, Redshift

---

## 🤝 Contributing

Contributions welcome! Please read `CONTRIBUTING.md` first.

**Areas for contribution:**
- Integration with more database systems
- ML models for predicting query carbon costs
- Visualization tools for developers
- Real-world case studies

---

## 📄 License

MIT License - See `LICENSE` file for details

---

## 📬 Contact

**Dilem Kaya**  
Digital Health Master Student  
Hasso Plattner Institute, Potsdam, Germany

**Research Supervisor:** Prof. Dr. Tilmann Rabl

---

## 🙏 Acknowledgments

- **Prof. Tilmann Rabl** - Sustainable Data Management lecture and Fair-CO₂ framework inspiration
- **Prof. Andreas Kipf** - Workload-driven optimizations and predicate caching insights
- **Fair-CO₂ Paper** - Han, L., Kakadia, J., Lee, B. C., & Gupta, U. (2025)

---

## 📊 Project Status

🚧 **Early Research Prototype** - Master's thesis project, Winter Semester 2025/26

**Roadmap:**
- ✅ Phase 1: Multi-dimensional attribution model
- 🔄 Phase 2: Query-level carbon measurement (in progress)
- 📅 Phase 3: Carbon-aware optimizer (planned Q2 2026)

---

## 📈 Citation

If you use this work, please cite:

```bibtex
@mastersthesis{kaya2026query,
  title={From Peak Awareness to Carbon-Aware Optimization: Fair Query-Level Attribution for Cloud Emissions},
  author={Kaya, Dilem},
  year={2026},
  school={Hasso Plattner Institute},
  type={Master's Thesis}
}
```




