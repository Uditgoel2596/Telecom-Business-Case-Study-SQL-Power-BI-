1 What is the distribution of churned customers by gender?

SELECT 
    gender, COUNT(customerID) as "Churned Customers"
FROM
    telecom.customer
WHERE
    churn = 1
GROUP BY gender;

--

2 Which internet service type has the highest churn rate?

SELECT 
    InternetService, COUNT(customerID) AS 'Churned Customers'
FROM
    customer
WHERE
    Churn = 1
GROUP BY InternetService
ORDER BY COUNT(customerID) DESC;

--

3 Are there any correlation between churn and payment methods?

SELECT 
    PaymentMethod, 
    AVG(Churn) AS ChurnRate
FROM 
    customer
GROUP BY 
    PaymentMethod
ORDER BY 
    ChurnRate DESC;

--

4 Are there any correlation between churn and contract types?

SELECT 
    Contract, 
    Avg(Churn) AS ChurnRate
FROM 
    customer
GROUP BY 
    Contract
ORDER BY 
    ChurnRate DESC;

--

5 Which combination of services (InternetService, PhoneService, MultipleLines) has the highest churn rate?

SELECT 
    InternetService,
    PhoneService,
    Multiplelines,
    AVG(Churn) AS ChurnRate
FROM
    customer
GROUP BY InternetService , PhoneService , Multiplelines
ORDER BY AVG(Churn) DESC;

--

6 Do customers with dependents have a higher churn rate than those without?

SELECT 
    Dependents, Sum(Churn) AS ChurnRate
FROM
    customer
GROUP BY Dependents;

--

7 How does the tenure of customers impact churn rate? 

SELECT 
    tenure, AVG(Churn)
FROM
    customer
GROUP BY tenure
ORDER BY AVG(Churn) DESC
LIMIT 20;

---





