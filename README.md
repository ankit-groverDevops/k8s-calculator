# Kubernetes Request & Limit Calculator

A lightweight **capacity-planning tool** for estimating Kubernetes CPU and memory requests/limits for Java, Python (Gunicorn), and Node.js applications.

The calculator lets you:

- Pick your application language.
- Adjust key tuning parameters via sliders (heap sizes, GC overhead, workers, etc.).
- Instantly view three recommended profiles:
  - **Minimal** – conservative starting point  
  - **Balanced** – common production baseline  
  - **Maximum** – for bursty or high-load scenarios

---

## 🚀 Getting Started

1. Clone or download this repository.  
2. Open `k8sCalculator.html` in any modern browser (no server needed).

> **Tip:** Keep the file with your infrastructure utilities so you can quickly size pods during design or review sessions.

---

## 🛠️ How It Works

- **Language selection** dynamically renders the relevant input sliders:
  - **Java** – Xms/Xmx, GC %, Metaspace, Thread stacks, JIT cache, GC structures, and other JVM internals.
  - **Python** – Gunicorn workers, memory per worker, master memory.
  - **Node.js** – Workers, memory per worker, master memory, overhead %, expected RPS.
- When you click **Calculate**, the script:
  1. Reads slider values.
  2. Applies language-specific formulas for memory and CPU.
  3. Outputs **Minimal / Balanced / Maximum** recommendations.

The formulas are based on JVM and GC best practices, Gunicorn sizing guidance, and Node.js (V8) memory behavior.

---

## 📌 Notes & Future Enhancements

- All numbers are heuristics; validate them against real workloads before deploying to production.
- For larger clusters or dynamic workloads, consider:
  - Integrating metrics from **Prometheus** or **metrics-server**.
  - Auto-discovery of live heap sizes (e.g., JFR, pprof).
  - Exporting results as YAML for direct use in Kubernetes manifests.

---

## 📷 Example Screenshot

![Example Screenshot](https://github.com/ankit-groverDevops/k8s-calculator/blob/main/docs/test.png)

---

## 📄 License

MIT License – you’re free to use, modify, and improve.
