# 🎯 Interactive Bayesian Decision Boundary Simulator

![UI Preview](newplot(2).png)


A modern, interactive web-based simulator for visualizing **Multivariate Bayesian Decision Boundaries**. Inspired by classic Pattern Recognition Java Applets, this tool allows users to dynamically manipulate Means (μ), Covariance Matrices (Σ), and Prior Probabilities to instantly see how probability density contours and decision boundaries (Linear and Quadratic) adapt in a 2D feature space.

### 🔗 [Click here for the Live Demo](https://aishwarya-926.github.io/bayes-boundary/) 


---

## ✨ Features

* **Full 2x2 Covariance Matrix Support:** Edit the diagonal (variance) and off-diagonal (covariance) terms. The tool automatically enforces matrix symmetry.
* **Real-time Visualization:** Watch the contours and decision boundaries warp, shift, and rotate instantly as you drag sliders or type numbers.
* **Linear vs. Quadratic Boundaries:** 
  * Set Σ₁ = Σ₂ to see a straight **Linear Discriminant**.
  * Make Σ₁ ≠ Σ₂ to generate parabolas, ellipses, and hyperbolas (**Quadratic Discriminants**).
* **Prior Probability Slider:** Shift the classification bias seamlessly and watch the boundary move.
* **Mathematical Validation:** Built-in safeguards ensure that input covariance matrices are valid (Positive-Definite / Determinant > 0), preventing math crashes.
* **Zero Dependencies:** Pure HTML, CSS, and JavaScript. Powered by the open-source [Plotly.js](https://plotly.com/javascript/) graphing library. No backend server required!

---

## 🚀 How to Run Locally

Because this project is entirely frontend-based, running it locally is incredibly simple.

1. **Clone the repository:**
   git clone https://github.com/yourusername/bayesian-decision-boundary.git

2. **Navigate to the folder:**
   cd bayesian-decision-boundary

3. **Open the file:**
   Simply double-click on `index.html` to open it in your default web browser (Chrome, Edge, Firefox, Safari).

---

## 🧠 The Math Behind the Visuals

This tool visualizes the fundamental concepts of Statistical Pattern Recognition and Bayesian Decision Theory. 

Given a 2D feature vector **x**, we classify it into Class 1 or Class 2 based on the **Maximum a Posteriori (MAP)** rule. The decision boundary represents the set of points where the posteriors are equal:

P(ω₁ | x) = P(ω₂ | x)

Using Bayes' Theorem and assuming the class-conditional probability densities p(x | ωᵢ) are Multivariate Gaussian distributions, the discriminant function gᵢ(x) for a class i is defined as:

gᵢ(x) = -0.5 * (x - μᵢ)^T * Σᵢ⁻¹ * (x - μᵢ) - 0.5 * ln|Σᵢ| + ln(P(ωᵢ))

### What to look for when playing with the tool:
* **Changing the Priors:** Modifying P(ω₁) simply shifts the boundary away from the more probable class.
* **Identical Covariances (Σ₁ = Σ₂):** The quadratic terms cancel out! The boundary becomes a perfectly straight line (a hyperplane).
* **Arbitrary Covariances (Σ₁ ≠ Σ₂):** The quadratic terms dominate, resulting in decision boundaries that are hyper-quadrics (ellipses, parabolas, or hyperbolas). Try making one class very "tight" (small variance) and one very "spread out" (large variance) to see an elliptical boundary completely encircle the tighter class!

---

## 🛠️ Tech Stack

* **HTML5 & CSS3:** For the modern, responsive dashboard layout.
* **Vanilla JavaScript (ES6):** For parsing matrices, validating positive-definiteness, and computing the 2D Gaussian density functions.
* **Plotly.js:** For rendering high-performance 2D contour maps, markers, and decision lines.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 
If you want to add new features (like a 3D surface plot toggle, or adding a third class), feel free to fork the repository and submit a pull request.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.
