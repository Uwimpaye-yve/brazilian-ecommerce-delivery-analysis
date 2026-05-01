Project Brief: The "Last Mile" Logistics Auditor
Client: Veridi Logistics (Global E-Commerce Aggregator)

Analyst: Uwimpaye Yvette

A. The Executive Summary
Our logistics audit confirms a direct link between delivery performance and customer sentiment. While the majority of orders are "On Time," there is a clear regional failure pattern where more remote states (such as RR, AM, and AP) experience disproportionate delays. Critically, "Super Late" deliveries (>5 days past estimate) result in a significant drop in average review scores—often falling below 1.5 stars—proving that logistics inaccuracies are the primary driver of negative customer reviews for Veridi Logistics.

B. Project Links
Link to Notebook: https://datastudio.google.com/reporting/e8379b46-15e0-44e0-8f8e-0d85dc85dc31

Link to Dashboard: https://datastudio.google.com/reporting/e8379b46-15e0-44e0-8f8e-0d85dc85dc31

Link to Presentation: https://docs.google.com/presentation/d/1n_MerSstKynQ6XgxEJd-Dydi_5a1IcmyJzQAi1ogL4s/edit?usp=sharing


C. Technical Explanation
Data Cleaning & Schema Building
Joins: I successfully integrated the Orders, Reviews, and Customers tables into a master dataset.

Row Duplication Prevention: To adhere to acceptance criteria, I performed a groupby and mean operation on the Reviews table before joining to ensure each order_id remained unique.

Data Types: All timestamp columns were converted to datetime objects to calculate precise delivery deltas.

Logistics Logic (The Delay Calculator)
I created a days_diff column calculating the variance between the Estimated Delivery Date and the Actual Delivery Date.

Orders were classified into three statuses: On Time, Late, and Super Late (for delays exceeding 5 days).

Canceled and unavailable orders were filtered out to ensure the audit reflected actual delivery performance.

Candidate's Choice: "The Expectation Gap"
Feature: I analyzed the "Promised Window" (the duration between the purchase date and the estimated delivery date).

Business Value: My analysis revealed that "Super Late" orders often had shorter-than-average promised windows for remote regions. This suggests that the current estimation algorithm is over-promising fast delivery in areas with known logistical bottlenecks. By recalibrating these estimates, Veridi Logistics can manage customer expectations and reduce negative sentiment even when physical transit times cannot be shortened.

📂 Repository Contents
Last_Mile_Logistics_Audit.ipynb: The full Python source code.

Last_Mile_Logistics_Audit.pdf: A PDF export of the notebook showing all charts and outputs.

README.md: Project summary and documentation.
