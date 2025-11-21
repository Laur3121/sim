# RasPi Thermal Simulator (RC-model + Migration)

This is a self-contained template to simulate node temperatures in a Raspberry Pi cluster
and evaluate migration policies (RoundRobin, CPU-based, Temp-aware).

## Quick Start
```bash
# (1) Ensure Python 3.9+ is available
# (2) Run the simulator
python src/main.py --config configs/cluster.yml --out results/run1
```

It will produce:
- CSVs in `results/run1/`
- Figures in `results/run1/figs/`

## Files
- `configs/cluster.yml`: Cluster + policy + plotting configuration
- `traces/ambient.csv`: Ambient temperature time-series (s, degC)
- `traces/cpu_node*.csv`: CPU% time-series (s, 0..100)
- `src/models.py`: RC thermal model (Node) & ClusterSim
- `src/scheduler.py`: Policies (RoundRobin/CPU/Temp-aware)
- `src/metrics.py`: Metrics aggregation
- `src/plots.py`: Matplotlib plots (1 chart per figure, no custom colors)
- `src/io_utils.py`: I/O utilities (CSV/YAML handling)
- `src/main.py`: Entrypoint

## Notes
- Plots follow simple Matplotlib defaults (no explicit colors), one chart per figure.
- You can swap synthetic traces with your real CSV logs (same columns: `time, value`).
# sim
