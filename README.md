\# Kubernetes Request \& Limit Calculator



A lightweight \*\*capacity-planning tool\*\* for estimating Kubernetes CPU and memory

requests/limits for Java, Python (Gunicorn) and Node.js applications.



The calculator lets you:



\- Pick your application language.

\- Adjust key tuning parameters via sliders (heap sizes, GC overhead, workers, etc.).

\- Instantly view three recommended profiles:

&nbsp; - \*\*Minimal\*\* – conservative starting point  

&nbsp; - \*\*Balanced\*\* – common production baseline  

&nbsp; - \*\*Maximum\*\* – for bursty or high-load scenarios



---



\## 🚀 Getting Started



1\. Clone or download this repository.

2\. Open the `k8sCalculator.html` file in any modern browser (no server needed).



> \*\*Tip:\*\* Keep the file with your infra utilities so you can quickly size pods during reviews.



---



\## 🛠️ How It Works



\- \*\*Language selection\*\* dynamically renders the relevant input sliders:

&nbsp; - \*\*Java\*\* – Xms/Xmx, GC %, Metaspace, Thread stacks, JIT cache, GC structures, etc.

&nbsp; - \*\*Python\*\* – Gunicorn workers, memory per worker, master memory.

&nbsp; - \*\*Node.js\*\* – workers, memory per worker, master memory, overhead %, expected RPS.

\- When you click \*\*Calculate\*\*, the script:

&nbsp; 1. Reads slider values.

&nbsp; 2. Applies language-specific formulas for memory and CPU.

&nbsp; 3. Outputs \*Minimal / Balanced / Maximum\* recommendations.



The formulas are intentionally simple — they’re based on JVM/GC rules of thumb,

Gunicorn best practices, and V8/Node memory patterns.



---



\## 📌 Notes \& Future Enhancements



\- Numbers are heuristics; validate them against real workloads before production rollout.

\- For large clusters, consider integrating:

&nbsp; - \*\*Prometheus / metrics-server\*\* for real usage telemetry.

&nbsp; - Auto-discovery of live heap sizes (JFR, pprof, etc.).

&nbsp; - Export of results to YAML (`requests`/`limits`) for direct use in manifests.



---



\## Example Screenshot



!\[Example Screenshot](docs/test.png)  

---



\## License



MIT – feel free to use and improve.



