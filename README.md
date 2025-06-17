# Top-1000-Youtubers-Analysis

## Problem Statement

As a youtube content creator or a marketing analyst, the goal is to gain insights into the performance and charateristics of the top 1000 youtubers based on their subscriber count. This analysis aims to provideactionable information for content creator, marketers, and stakeholdersto make informed decision and optimized strategies for content creation, audience engagement, and channel growth.
### Key Questions:
### Overview of Top 1000 Youtubers distribution:
- Provide a concise overview of the top 1000 Youtubers, focusing on average subscriber count, likes, visits, and comments.Additionally analyse the diversity in terms of the number of countries and content categories represented.
### Audience Segmentation:
- How are the top 1000 Youtubers distributed across different categories or genres?
- What are the most popular content categories among the top Youtubers?
### Geographical Analysis:
- What is the distribution of top Youtubers based on their country of origin?
### Subscriber Engagement:
- What is the average number of visits, likes, and comments per video for the top Youtubers?
- Is there a correlation between subscriber count and engagement metrics?
### Top Performance Identification:
- Who are the top 10 Youtubers based on subscriber count?
- What are the common characteristics or strategies among these top performers?
### Content and Channel Recommendation:
- Are there any specific content categories that show a higher engagement rate?
### Cross-Country Subscriber Engagement Comparision:
- For global content creators and marketers, understanding variations in subscriber engagement across the different countries.

For this project we did 2 different approches for data analysis first with SQL quries and then secondly with Power BI software for data visualization.

## SQL Data Analysis

### Problem Statement & Solution:

1) Overview of Top 1000 Youtubers distribution:

Question: Provide a concise overview of the top 1000 Youtubers, focusing on average subscriber count, likes, visits, and comments.Additionally analyse the diversity in terms of the number of countries and content categories represented.

Query:

    SELECT 
    COUNT(DISTINCT Country) AS Total_countries,
    COUNT(DISTINCT Categories) AS total_categories,
    AVG(Suscribers) AS avg_suscribers,
    AVG(Visits) AS avg_visits,
    AVG(Likes) AS avg_likes,
    AVG(Comments) AS avg_comments
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]

2) Audience Segmentation:

Question: How are the top 1000 Youtubers distributed across different categories or genres? What are the most popular content categories among the top Youtubers?

Query:

    SELECT 
    Categories,
    COUNT(Username) AS Total_channel
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    GROUP BY Categories
    ORDER BY Total_channel DESC

3) Geographical Analysis:

Question: What is the distribution of top Youtubers based on their country of origin?

Query:

    SELECT TOP 10
    Country,
    COUNT(Username) AS Total_channel
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    GROUP BY Country
    ORDER BY Total_channel DESC

4) Subscriber Engagement:
   
Question: What is the average number of visits, likes, and comments per video for the top Youtubers? Is there a correlation between subscriber count and engagement metrics?

Query:

    SELECT TOP 10
    Username,
    AVG(Suscribers) AS avg_suscribers,
    AVG(Visits) AS avg_visits,
    AVG(Likes) AS avg_likes,
    AVG(Comments) AS avg_comments
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    GROUP BY Username
    ORDER BY avg_suscribers

5) Top Performance Identification:
   
Question: Who are the top 10 Youtubers based on subscriber count? What are the common characteristics or strategies among these top performers?

Query:

    SELECT TOP 10
    Username,
    Suscribers,
    Country
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    ORDER BY Suscribers DESC

6) Content and Channel Recommendation:
   
Question: Are there any specific content categories that show a higher engagement rate?

Query:

    SELECT TOP 10
    Categories,
    AVG(Suscribers) AS avg_suscribers,
    AVG(Visits) AS avg_visits,
    AVG(Likes) AS avg_likes,
    AVG(Comments) AS avg_comments
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    GROUP BY Categories
    ORDER BY avg_suscribers DESC

7) Cross-Country Subscriber Engagement Comparision:
   
Question: For global content creators and marketers, understanding variations in subscriber engagement across the different countries.

Query:

    SELECT TOP 10
    Country,
    AVG(Suscribers) AS avg_suscribers,
    AVG(Visits) AS avg_visits,
    AVG(Likes) AS avg_likes,
    AVG(Comments) AS avg_comments
    FROM [Clean_Top_1000_Youtube_df - youtubers_df]
    GROUP BY Country
    ORDER BY avg_suscribers DESC


## Data Analysis & Visualization Using Power BI
### Results and Insights:

