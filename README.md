# SoftDrink TrendsAnalysis
SoftDrink TrendsAnalysis: A Tableau dashboard project providing comprehensive insights into soft drink sales trends, allowing for detailed analysis and informed decision-making within the beverage industry.

<div class='tableauPlaceholder' id='viz1710323381098' style='position: relative'><noscript><a href='#'><img alt='Year to Month Calendar ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Fi&#47;FizzFlowFromYearlyInsightstoMonthlyMovesinSoftDrinkSales&#47;YeartoMonthCalendar&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='FizzFlowFromYearlyInsightstoMonthlyMovesinSoftDrinkSales&#47;YeartoMonthCalendar' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Fi&#47;FizzFlowFromYearlyInsightstoMonthlyMovesinSoftDrinkSales&#47;YeartoMonthCalendar&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                       


# LOD CALCULATIONS: This is a Tableau calculated field that categorizes the profit based on different ranges and labels them accordingly.

    The { FIXED [Purchase Date] : SUM([Profit])} part calculates the total profit for each unique purchase date.

    The entire expression is wrapped within an IF...ELSEIF...ELSE structure to handle different profit ranges.

    Here's what each part of the calculation does:
        IF { FIXED [Purchase Date] : SUM([Profit])} <= -10000 THEN '-20K to -10K': This checks if the total profit for a particular purchase date is less than or equal to -10000. If it is, it assigns the label '-20K to -10K'.
        ELSEIF { FIXED [Purchase Date] : SUM([Profit])} > -10000 AND { FIXED [Purchase Date] : SUM([Profit])} < 0 THEN '-10K to 0K': This checks if the total profit is greater than -10000 but less than 0. If true, it assigns the label '-10K to 0K'.
        ELSEIF { FIXED [Purchase Date] : SUM([Profit])} >= 0 AND { FIXED [Purchase Date] : SUM([Profit])} < 10000 THEN '0K to 10K': This checks if the total profit is greater than or equal to 0 but less than 10000. If true, it assigns the label '0K to 10K'.
        ELSEIF { FIXED [Purchase Date] : SUM([Profit])} >= 10000 AND { FIXED [Purchase Date] : SUM([Profit])} < 20000 THEN '10K to 20K': This checks if the total profit is greater than or equal to 10000 but less than 20000. If true, it assigns the label '10K to 20K'.
        ELSEIF { FIXED [Purchase Date] : SUM([Profit])} >= 20000 AND { FIXED [Purchase Date] : SUM([Profit])} < 30000 THEN '20K to 30K': This checks if the total profit is greater than or equal to 20000 but less than 30000. If true, it assigns the label '20K to 30K'.
        ELSE '30K to 40K': If none of the above conditions are met, it assigns the label '30K to 40K'.
![image](https://github.com/vbhatsaccnt/SoftDrinkTrendsAnalysis/assets/67544433/65b6c2cc-23c6-47d1-8c4b-d5efb60a94b6)
