# Secure Hash Standard (SHS) – SHA-256 Implementation  

This repository contains a **complete, professional, and fully documented** implementation of the core components of the **SHA-256** algorithm as specified in the NIST Secure Hash Standard (FIPS PUB 180-4).

All work is presented in a single, clean, reproducible Jupyter notebook: **`problems.ipynb`**

## 🎯 Project Overview

This implementation focuses on the cryptographic primitives of the Secure Hash Standard, specifically SHA-256 as defined in **FIPS PUB 180-4, Section 4.1.2**. The project demonstrates a comprehensive understanding of:

- **32-bit word manipulation** using NumPy for correct overflow behavior
- **Bitwise operations** fundamental to cryptographic hash functions  
- **SHA-256 algorithmic components** including constants generation, message padding, and compression
- **Security analysis** through practical password cracking demonstrations

---

## Problems Status

| Problem | Status        | Description |
|--------|---------------|-----------|
| 1      | ✅ Completed  | 32-bit operations: `Parity`, `Ch`, `Maj`, `Σ₀`, `Σ₁`, `σ₀`, `σ₁` using safe `numpy.uint32` |
| 2      | ✅ Completed  | Generation of SHA-256 constants K[0..63] from fractional parts of cube roots of first 64 primes |
| 3      | ✅ Completed  | Generator `block_parse(msg)` – correct SHA-256 padding per FIPS 180-4 §5.1.1 & §5.2.1 |
| 4      | ✅ Completed  | `hash(current, block)` – SHA-256 compression function (§6.2.2) |
| 5      | ✅ Completed  | Password cracking + comprehensive security analysis with recommendations |

> **All problems completed!** Full implementation with detailed documentation, testing, and references.

---

## 🚀 Environment Setup

This project requires Python 3.x and relies primarily on the **NumPy** library for safe 32-bit word manipulation that enforces proper modulo 2³² arithmetic as required by SHA-256.

### Prerequisites
- **Python 3.8+** (tested with Python 3.12)
- **pip** package manager
- **Git** (for cloning)

### Step-by-Step Setup Instructions

```bash
# 1. Clone the repository
git clone https://github.com/PhatTanNguyen45/computational_theory.git
cd computational_theory

# 2. Create and activate virtual environment (RECOMMENDED)
python -m venv venv

# Activate on Linux/macOS:
source venv/bin/activate

# Activate on Windows:
.\venv\Scripts\activate

# 3. Install all dependencies from requirements.txt
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter notebook
```

**Important**: Open `problems.ipynb` and run cells sequentially starting from the first imports cell. Every cell is designed to run out-of-the-box with detailed explanations, tests, and references.

### Dependencies Explained

- **NumPy ≥1.21.0**: Essential for `uint32` type that provides correct 32-bit arithmetic with automatic wraparound at 2³²
- **Jupyter ≥1.0.0**: Interactive notebook environment for presentation and testing
- **Python Standard Library**: All other operations use built-in functions (no additional external dependencies)

The implementation deliberately uses minimal dependencies to focus on algorithmic understanding rather than library usage.

---

## 📚 Key Reference Documentation

This entire project is based on official cryptographic standards and academic sources:

### Primary Reference
- **[NIST FIPS PUB 180-4 - Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf)**  
  The authoritative specification that defines all SHA-256 operations, constants, and procedures implemented in this project. Specifically:
  - **Section 4.1.2**: Defines the seven logical functions implemented in Problem 1
  - **Section 4.2.2**: Specifies the 64 constants K₀–K₆₃ derived from cube roots of primes (Problem 2)
  - **Section 5.1.1**: Message padding algorithm with deterministic length encoding (Problem 3)
  - **Section 5.2.1**: Message parsing into 512-bit blocks for processing (Problem 3)  
  - **Section 6.2.2**: Complete SHA-256 hash computation and compression function (Problem 4)

### Supporting References  
- **[NIST SP 800-107 - Recommendation for Applications Using Approved Hash Algorithms](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-107r1.pdf)**: Security guidance and best practices
- **[RFC 6234 - US Secure Hash Algorithms](https://tools.ietf.org/rfc/rfc6234.txt)**: Alternative specification with additional implementation details

All mathematical formulas, constants, and algorithmic steps in the notebook directly correspond to these official standards, ensuring compliance and correctness.

---

## Repository Structure

```bash
├── problems.ipynb                  # Main assessment notebook (Problems 1–5 complete)
├── requirements.txt               # Minimal dependencies
├── README.md                       # This comprehensive documentation file
├── .gitignore                      # Clean Python + Jupyter setup
```

## Key Features

- ✅ 100% compliant with FIPS 180-4 specification
- ✅ Uses only numpy.uint32 → prevents integer overflow bugs
- ✅ **Comprehensive documentation**: Every function has detailed docstrings
- ✅ **Rich narrative**: Extensive Markdown cells explain context, motivation, and theory
- ✅ **Inline comments**: Important code statements are explained
- ✅ **Verified against NIST test vectors**: All implementations tested
- ✅ **Professional structure**: Clean code organization with meaningful commits
- ✅ **Contextualized references**: Citations placed where relevant with explanations

---

## 🔗 References and External Resources

### Primary Cryptographic Standards
- **[NIST FIPS PUB 180-4 - Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf)**  
  **Why relevant:** The authoritative specification defining all SHA-256 operations implemented in this project. Every algorithm, constant, and procedure directly follows this standard.

- **[NIST SP 800-63B - Digital Identity Guidelines](https://pages.nist.gov/800-63-3/sp800-63b.html)**  
  **Why relevant:** Provides modern password security requirements used in Problem 5's security recommendations, including salt requirements and password policies.

### Password Security Resources  
- **[OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)**  
  **Why relevant:** Industry best practices for secure password hashing used in Problem 5's security analysis and recommendations.

- **[Argon2 RFC 9106](https://www.rfc-editor.org/rfc/rfc9106.html)**  
  **Why relevant:** Specification for the recommended password hashing algorithm discussed in Problem 5's security improvements section.

### Technical Implementation Resources
- **[NumPy uint32 Documentation](https://numpy.org/doc/stable/reference/arrays.scalars.html#numpy.uint32)**  
  **Why relevant:** Essential for understanding the 32-bit arithmetic used throughout the SHA-256 implementation to ensure correct modulo 2³² operations.

- **[Python Generator Functions Guide](https://realpython.com/introduction-to-python-generators/)**  
  **Why relevant:** Explains the generator pattern used in Problem 3's `block_parse()` function for memory-efficient message processing.

- **[Python Bytes and Encoding](https://realpython.com/python-bytes/)**  
  **Why relevant:** Understanding byte manipulation is crucial for the message padding and block processing implemented in Problems 3-5.

### Security Research and Tools
- **[Have I Been Pwned API](https://haveibeenpwned.com/API/v3)**  
  **Why relevant:** Referenced in Problem 5 as a tool for checking passwords against known breach databases.

- **[Daniel Miessler's SecLists](https://github.com/danielmiessler/SecLists)**  
  **Why relevant:** Source of password dictionaries mentioned in Problem 5's dictionary attack methodology.

---

## 📖 How to Use This Repository

### Quick Start (For Reviewers)
```bash
# Clone and enter repository
git clone https://github.com/PhatTanNguyen45/computational_theory.git
cd computational_theory

# Install dependencies and start Jupyter
pip install -r requirements.txt
jupyter notebook

# Open problems.ipynb and run cells from top to bottom
```

### Detailed Usage Instructions

1. **Environment Setup**: Ensure Python 3.8+ is installed with pip package manager
2. **Dependency Installation**: Run `pip install -r requirements.txt` to install NumPy and Jupyter
3. **Notebook Execution**: 
   - **IMPORTANT**: Before every run, restart the Python kernel (`Kernel > Restart`) 
   - Run cells **sequentially** from top to bottom to ensure proper state management
   - Each problem builds on previous ones - skipping cells will cause errors
4. **Problem Navigation**: Use notebook headings to navigate to specific problems (1-5)
5. **Testing**: Each problem includes comprehensive test cases that verify correctness

### Understanding the Implementation

**For Cryptography Students:**
- Focus on the mathematical foundations explained in Markdown cells
- Study how each FIPS 180-4 section maps to code implementation
- Review test cases to understand expected input/output relationships

**For Security Practitioners:**
- Problem 5 demonstrates practical password security vulnerabilities
- Security recommendations section provides actionable guidance
- Dictionary attack implementation shows real-world attack methodology

**For Software Developers:**
- Code demonstrates proper cryptographic implementation practices
- Shows correct handling of 32-bit arithmetic and byte operations
- Illustrates professional documentation and testing approaches

---
