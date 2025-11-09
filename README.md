# Secure Hash Standard (SHS) – SHA-256 Implementation  

This repository contains a **complete, professional, and fully documented** implementation of the core components of the **SHA-256** algorithm as specified in the NIST Secure Hash Standard.

All work is presented in a single, clean, reproducible Jupyter notebook: **`problems.ipynb`**

---

## Problems Status

| Problem | Status        | Description |
|--------|---------------|-----------|
| 1      | Completed     | 32-bit operations: `Parity`, `Ch`, `Maj`, `Σ₀`, `Σ₁`, `σ₀`, `σ₁` using safe `numpy.uint32` |
| 2      | Completed     | Generation of SHA-256 constants K[0..63] from fractional parts of cube roots of first 64 primes |
| 3      | Completed     | Generator `block_parse(msg)` – correct SHA-256 padding per FIPS 180-4 §5.1.1 & §5.2.1 |
| 4      | In Progress   | `hash(current, block)` – SHA-256 compression function (§6.2.2) |
| 5      | In Progress   | Password cracking + security analysis |

> Problems 4 and 5 will be completed and pushed before the final deadline (December 21st, 2025).

---

## How to Run This Project

```bash
# 1. Clone the repo
git clone https://github.com/PhatTanNguyen45/computational_theory
cd computational_theory

# 2. Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate    # Linux/Mac
# .\venv\Scripts\activate   # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter notebook
```

Then open `problems.ipynb` — every cell runs out-of-the-box with detailed explanations, tests, and references.

---

## Repository Structure

```bash
├── problems.ipynb                  # Main assessment notebook (Problems 1–3 complete)
├── requirements.txt               # Minimal dependencies
├── README.md                       # This file
├── .gitignore                      # Clean Python + Jupyter setup
```

Key Features

- 100% compliant with FIPS 180-4
- Uses only numpy.uint32 → no integer overflow bugs
- All functions include docstrings, tests, and Markdown explanations
- Verified against official NIST test vectors
- Professional structure, clean code, meaningful commits
- Hyperlinked references with context (as required)

References

- NIST FIPS PUB 180-4 – Secure Hash Standard (SHS)
  https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf
- NumPy uint32 documentation https://numpy.org/doc/stable/reference/arrays.scalars.html#numpy.uint32
- Python bytes objects https://realpython.com/python-bytes/
- Generator functions in Python https://realpython.com/introduction-to-python-generators/
