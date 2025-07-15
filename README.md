This project developed a **Business Intelligence (BI) solution for TelecomPlus**, a national telecommunications company operating in a highly competitive market. The primary goal was to enable the company to **make data-driven decisions** and gain deeper insights into its performance, addressing key business questions about customer satisfaction, service quality, customer preferences, product trends, revenue trends, and market performance.

TelecomPlus faced several significant challenges that the BI solution aimed to overcome:
*   **Inconsistent Service Quality Across Channels**: They lacked a clear understanding of the performance of their communication channels, making it difficult to identify bottlenecks like excessive wait times or prolonged resolution times in customer service.
*   **Products That Don’t Fit Local Needs**: The company didn't fully understand regional customer preferences, potentially missing opportunities to connect with customers and build loyalty by offering unsuitable products.
*   **Unclear Revenue Sources and Growth Opportunities**: It was unclear which locations and products were generating the most revenue, risking misinvestment and missed growth opportunities.

To tackle these issues, a comprehensive BI system was developed using **Microsoft Fabric**, **Power BI**, and **Power BI Report Builder**.

Here's how each component was implemented:

*   **Data Warehouse**:
    *   Designed following a **star schema**, it includes two fact tables (`fact_customer_interactions_cases` and `fact_signups_record`) and six dimension tables (`DIM_DATE`, `DIM_CUSTOMER`, `DIM_AGENT`, `DIM_CHANNEL`, `DIM_PLAN`, `DIM_REASON`).
    *   All data was **cleaned and prepared** through a structured ETL (Extract, Transform, Load) process using **Microsoft Fabric pipelines and Dataflows Gen2**.

*   **Semantic Model**:
    *   **Built on Microsoft Fabric**, this model serves as a crucial step to answer business questions and provide insights to TelecomPlus.
    *   It offers an additional layer that explains relationships between data sources based on business logic and information needs.
    *   A key aspect was **renaming tables and attributes into user-friendly names** (e.g., `Dim_agent` became `D Agent`, `fact_signups_record` became `F Signups Record`) to facilitate understanding for in-depth analysis.
    *   This model includes **dimensions that provide context** and **calculated measures and KPIs** to quantify business performance.

*   **Calculated Measures & KPIs (Key Performance Indicators)**:
    *   Essential metrics were defined within the semantic model to track customer acquisition, service quality, and financial performance.
    *   **Yearly Signup Growth Rate (YSGR)**: Compares current signups to the previous year, with a **target of 8.5% annual growth** to address shareholder concerns about long-term profitability.
    *   **Average Satisfaction Score (ASS)**: Monitors customer satisfaction, with a **minimum acceptable target of 4.0 out of 5** to enhance customer loyalty and reduce churn, as scores below 4.0 are linked to higher customer attrition.
    *   **Year-over-Year (YoY) Revenue Growth Percentage**: Compares current revenue to the previous year, with a **target of 6% annual growth**, slightly higher than their historical average of 5%.

*   **Interactive Dashboards & Reports**:
    *   A visual dashboard with **seven pages**, including two embedded paginated reports, was **developed in Power BI**.
    *   Pages include:
        *   **Executive Business Overview**: Summarizes the three primary KPIs and their trends from 2017 to 2022. Gauges are used for immediate progress assessment towards targets, and line charts show trends over time.
        *   **Service Quality & Experience**: Explores the Average Satisfaction Score KPI in detail, breaking it down by department and channel, and provides metrics like interaction volume, waiting, and resolution times. Small multiples and bar charts are used to identify bottlenecks and areas for improvement.
        *   **Customer Preferences (Pages 1 and 2)**: Provides statistics on total signups, their evolution over time, and a breakdown by age group, gender, and region. Page 1 uses bar charts with small multiples to show product popularity by demographics, while Page 2 uses a combination of maps, horizontal bar charts, and a navigation bar for exploring top products by region.
        *   **Revenue Analysis and Market Performance**: Analyzes revenue growth percentage and absolute values, showing the top three regions with the highest revenue and annual revenue changes by product category.
    *   **Power BI Desktop** was used for integrating paginated reports and connecting them with slicers for user interaction. Various chart types like bar charts and line charts were chosen to address specific business needs.
    *   **User Experience Enhancements** in Power BI include page-based report tooltips for map visualizations, which display a bar chart of cities with the most signups when hovering over a state's bubble. Hierarchical drill-down navigation was implemented with **bookmarks** to streamline the experience for complex charts.

*   **Paginated Reports**:
    *   Two detailed paginated reports, "Revenue by Product Name" and "Top 3 products by region and year," were **designed using Power BI Report Builder**.
    *   This specialized tool was chosen due to **known limitations of Microsoft Fabric Services in designing and customizing paginated reports**.
    *   Report Builder allowed for enhanced formatting (headers, logos, colored header rows, centered text), application of filters (e.g., displaying Top 3 products using DAX measures), and sorting rules for organized presentation.
    *   **Parameters were created in Report Builder** to control the data displayed, allowing users to filter information by region for a clearer view.
    *   After creation, these reports were **published on Fabric** to be included and synchronized within the main Power BI dashboard.

The successful implementation of this BI solution marks a transformative step for TelecomPlus, enabling them to **improve operational efficiency, enhance customer satisfaction and loyalty, capitalize on growth opportunities, and strengthen their competitive position**. The project transformed raw data into actionable knowledge that is fundamental to data-driven decision-making, directly addressing their long-standing operational challenges and strategic objectives.

Key lessons learned during the project include:
*   The **importance of continuously iterating with end-users** to refine how data is presented to best support decision-making.
*   The value of **understanding the strengths and weaknesses of different tools** within a BI ecosystem (like Microsoft Fabric, Power BI, and Power BI Report Builder) and effectively combining them to meet specific reporting needs.
*   The **critical role of the semantic model** in bridging the gap between technical data infrastructure and business logic by using user-friendly names and logical sorting.
*   The significance of **enhancing user experience** through features like tooltips and hierarchical navigation, which add substantial value to the final BI solution.
