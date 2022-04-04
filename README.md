# GA-Optimization-Bank-Lending-Decision-


## **Problem Statement**

During any financial crisis, there is very limited credit available within the banking sector. This has to be managed to distribute the limited credit available in a way that maximizes their profits in the time of crisis .Therefore, there is a need to set an optimal mechanism of bank lending decisions that will maximize the bank profit in a timely manner.The paper therefore proposes a model based on Genetic Algorithm (GA) to organize bank lending decision in a highly competing environment with credit crunch constraint.

## **Introduction**

This project deals with the implementation of Genetic Algorithms and Amalgamation of Genetic Algorithm with Simulated Annealing, to make Bank Lending Decision.

The objectives of the model are:

1) Determine a bank lending decision that maximizes bank profit
2) Determine a bank lending decision that minimizes the crediting cost

## **Methodology**

In the proposed method, the lending decision is dynamically decided based on customer&#39;s loan characteristics. It is assumed that all customers are applicable (good) to get the required loan.GA is employed to search for the most suitable customers depending on a set of factors such as loan age, loan size, loan interest rate, loan type, and borrower credit rating.Moreover, bank variables that are considered for selecting this optimal solution are loan interest rate, expected loan loss ,deposit rate ,reserve ratio, transaction cost .

![](RackMultipart20220404-4-s6l2c6_html_b7262a74f75c676d.png)

## **Variables used**

**1) Loan Age (α)** – No. of years for repaying the loan

**2) Credit Limit –** Maximum loan amount a borrower is eligible for.

3) **Loan Size (L)** – amount of loan requested by a specific customer

**4) Loan Interest Rate (rL) –** Interest rates are determined using loan age and loan type. These are defined for each borrower based on the mentioned parameters.

**5) Expected Loan Loss (λ) –**Borrow Credit Rating is used to measure the range of the expected

![](RackMultipart20220404-4-s6l2c6_html_ad73ca0e13b051d4.png) ![](RackMultipart20220404-4-s6l2c6_html_40ec61c6a0c2d215.png)

![](RackMultipart20220404-4-s6l2c6_html_ba0e22814cbf6b9c.png)

![](RackMultipart20220404-4-s6l2c6_html_5d7ecf06f3f74151.png)

The above data is to be used while implementing the GA or GA-SA algorithms.

## **Genetic Algorithm Fitness Function**

Fitness function Fx is given by the formula:

![](RackMultipart20220404-4-s6l2c6_html_86173cbdf1819e7a.png)

• **Loan Revenue (ϑ)**

The value of the loan revenue is calculated using the loan interest rate (rL), loan size (L), and the expected loan loss (λ ).

![](RackMultipart20220404-4-s6l2c6_html_77b57949fc45550f.png)

• **Loans Cost (μ)**

The value of the loan cost is determined using the loan size (L) and the predetermined institutional cost (δ).

![](RackMultipart20220404-4-s6l2c6_html_3f544ed16a8e4c58.png)

• **Total Transaction Cost (ϖ)**

The value of the total transaction cost is determined using institute transactional cost (T) and the customer transaction rate (rT). The value of rT has been assumed to be 0.01 for the purpose of this project.

Here, the institute transactional cost (T) is determined using the below formula:

T = (1-K)D

![](RackMultipart20220404-4-s6l2c6_html_5ff315358bd2cea.png)

• **Cost of Demand deposit (β)**

The value is determined using the bank&#39;s deposit interest rate (rD) and the bank&#39;s deposit (D)

![](RackMultipart20220404-4-s6l2c6_html_32f2823c9cde4504.png)

## **GA Validation Process to Generate a GA population with n chromosomes**

In the given data, we have 10 customers, so size of each chromosome is 1x10 , where each bit consists of 1 or 0 depending upon, whether the customer has been lent the loan or not. When we initially generate a population of chromosomes , many of them might be exceeding the credit constraints of the banks .The chromosomes which do not satisfy the credit crunch constraint are discarder .This can be done by calculating the total amount of loan allocation for a solution and comparing it with the total allowable loan amount of the bank.

![](RackMultipart20220404-4-s6l2c6_html_a894edd65adf9df4.png)

## **Genetic Algorithm Pseudo Code**

- Generate Initial Population that satisfies GA Validation Process.
- For n iterations:

-Evaluate Fitness of Each Lending Decision in the population

-Perform Roulette Wheel Selection to get Parent Pool

-Create New Generation Population using Reproduction, Crossover and Mutation

-Perform Forceful Crossover in case no solution generated in new generation

-Check Validity of solutions in New Generation Population

-Store Best Solution of each generation

- Plot and display best Solution

## **GA Results**

&quot;Best Fitness Value &quot; &quot;6.8352&quot;

&quot;Best Bank Lending…&quot; &quot;1&quot; &quot;0&quot; &quot;1&quot; &quot;1&quot; &quot;0&quot; &quot;1&quot; &quot;0&quot; &quot;0&quot; &quot;1&quot; &quot;1&quot;

So, we should lend money to

&quot; Customer&quot; &quot;1&quot; &quot;--Rating&quot; &quot;AAA&quot;

&quot; Customer&quot; &quot;3&quot; &quot;--Rating&quot; &quot;A&quot;

&quot; Customer&quot; &quot;4&quot; &quot;--Rating&quot; &quot;AA&quot;

&quot; Customer&quot; &quot;6&quot; &quot;--Rating&quot; &quot;AAA&quot;

&quot; Customer&quot; &quot;9&quot; &quot;--Rating&quot; &quot;A&quot;

&quot; Customer&quot; &quot;10&quot; &quot;--Rating&quot; &quot;A&quot;

![](RackMultipart20220404-4-s6l2c6_html_13c142a6c8e60f9e.png) ![](RackMultipart20220404-4-s6l2c6_html_e6cad6bd16569caa.png)

## **Genetic Algorithm-Simulated Annealing(GA-SA) Pseudo Code**

- Generate Initial Population that satisfies GA Validation Process.
- For n iterations:

-Evaluate Fitness of Each Lending Decision in the population

-Perform Roulette Wheel Selection to get Parent Pool

-Create New Generation Population using Reproduction, Crossover and Mutation

-Perform Forceful Crossover in case no solution generated in new generation

-Simulated Annealing Loop

While T\&gt;Tmin:

For k iterations:

For each chromosome:

-generate neighbourhood solution by swapping bits

-calculate fitness and compare with fitness of parent

-if fitness of neighbour \&lt; fitness of parent:

Accept solution with Metropolis Criterion

-else keep original sol.

-T=t\*c --- cooling

-Check Validity of solutions in New Generation Population

-Store Best Solution of each generation

- Plot and display best Solution

## **GA-SA Results**

&quot;Best Fitness Value &quot; &quot;6.5293&quot;

&quot;Best Bank Lending…&quot; &quot;1&quot; &quot;0&quot; &quot;1&quot; &quot;0&quot; &quot;0&quot; &quot;1&quot; &quot;0&quot; &quot;1&quot; &quot;1&quot; &quot;1&quot;

So, we should lend money to

&quot; Customer&quot; &quot;1&quot; &quot;Rating&quot; &quot;AAA&quot;

&quot; Customer&quot; &quot;3&quot; &quot;Rating&quot; &quot;A&quot;

&quot; Customer&quot; &quot;6&quot; &quot;Rating&quot; &quot;AAA&quot;

&quot; Customer&quot; &quot;8&quot; &quot;Rating&quot; &quot;AAA&quot;

&quot; Customer&quot; &quot;9&quot; &quot;Rating&quot; &quot;A&quot;

&quot; Customer&quot; &quot;10&quot; &quot;Rating&quot; &quot;A&quot;

![](RackMultipart20220404-4-s6l2c6_html_b048d51ac1de612.png)

## **Comparison of GA and GA-SA-amalgamation**

- It is observed that GA gives better solution than GA-SA. The best fitness value obtained using GA is 6.8352 whereas best fitness using GA-SA is 6.5293.
- Using GA , the loan is lent to customers – 1,3,4,6,9,10 and using GA-SA we get customers 1,3,6,8,9,10.
- The solution in GA converges faster , but it starts to fluctuate wildly after some iterations. However, in GA-SA the solution initially fluctuates and then reaches convergence with increase in iterations.
- Thus we can conclude that although GA gives better solutions , it is not as stable as GA-SA. Both algorithms give good results and are hence good algorithms to be used , depending on the use case.
