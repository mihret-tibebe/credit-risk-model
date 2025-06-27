## Credit Scoring Business Understanding

### 1. How does the Basel II Accord’s emphasis on risk measurement influence our need for an interpretable and well-documented model?

The Basel II Capital Accord establishes guidelines for banks to quantify and manage credit risk, placing significant importance on **risk measurement and transparency**. Under Basel II, institutions must demonstrate that their models for estimating credit risk are robust, interpretable, and explainable to regulators and auditors.

This means black-box models lacking documentation can undermine trust and make it difficult to justify lending decisions. Therefore, it’s essential to prioritize models that produce **clear, interpretable outputs** — such as Logistic Regression with Weight of Evidence (WoE) features — while maintaining thorough documentation of the model’s logic, assumptions, and performance. Such transparency ensures compliance with Basel II requirements and builds confidence among regulators, internal stakeholders, and customers.

---

### 2. Since we lack a direct "default" label, why is creating a proxy variable necessary, and what are the potential business risks of making predictions based on this proxy?

In our dataset, we do not have explicit information on whether customers **defaulted on loans**, which is the most direct measure of credit risk. Therefore, we must construct a **proxy variable** — for example, by clustering customers using RFM (Recency, Frequency, Monetary) metrics and labeling disengaged customers as high risk.

However, relying on a proxy introduces **business risks**:

* **Labeling bias:** Customers labeled high risk may not actually default, resulting in potential rejection of creditworthy applicants.
* **Overfitting to behavioral patterns:** The proxy may capture patterns specific to historical behavior in the dataset but fail to generalize to future customers.
* **Regulatory scrutiny:** Regulators may question the validity of models built on indirect or subjective proxies instead of real credit outcomes, which could complicate compliance efforts.

Therefore, careful validation and continuous monitoring are necessary to minimize these risks and adapt the model as actual repayment behavior becomes available.

---

### 3. What are the key trade-offs between using a simple, interpretable model (like Logistic Regression with WoE) versus a complex, high-performance model (like Gradient Boosting) in a regulated financial context?

In a regulated environment like credit risk assessment:

* **Simple models (e.g., Logistic Regression with WoE):**

  * **Pros:** High interpretability; coefficients directly relate to risk factors; easier to explain to regulators and business stakeholders; better suited to meet compliance standards.
  * **Cons:** May have limited predictive power, especially when the data contains non-linear patterns.

* **Complex models (e.g., Gradient Boosting Machines):**

  * **Pros:** Can capture complex, non-linear relationships; potentially higher predictive performance.
  * **Cons:** Difficult to interpret; “black-box” nature can raise concerns with regulators; more challenging to justify decisions, which can slow down approval and auditing processes.

Choosing between these involves balancing **regulatory requirements** for transparency with the **business need** for predictive accuracy. In some cases, combining both — e.g., using complex models for internal decision support but simpler models for customer-facing or regulatory explanations — may be an effective compromise.
