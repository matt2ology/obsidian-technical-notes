---
aliases: 
note-type: permanent
date-created: 2024-05-27
long-form-date-created: Monday, May 27, 2024
week-created: Week 22.1
time-created: 06:25 PM
---

# Colorado University Outreach Example Interview Questions

Related : [Technical Interview - README](../README.md)

Source : [CU_InterviewQuestions_v1](../../attachments/CU_InterviewQuestions_v1.pdf)

## General

1. Sell your college to me?
2. Explain to me why GPA does or does not matter.
3. Tell me something about yourself? 4. How long would you expect to work for us if hired?
5. Why are you the best person for this position?
6. Your preferred job location?
7. What signs of trust have you demonstrated in the past while working?
8. Why do you want to work for us?
9. Tell me about your favorite Teacher you've had in the past?
10. What's your ideal company to work for?
11. What is the toughest problem you've had to face? And how did you overcome it?
12. Do you know anyone from our company? How?
13. Tell me about a time when you were particularly effective on prioritizing tasks and completing a project on schedule?
14. What are your main weakness and how you are overcoming them?
15. Have you ever dealt with a stressful situation?
16. What are some of the aspects that you like about this job?
17. Tell me about any event you have organized and how you handled budget for that that event?
18. Are you a team player?
19. What are the goals you have set for you in life?
20. Tell me a time when you had to handle something drastic, but no one was around, how did you do it?
21. Are you okay working without a break if the company needs it?
22. What are you passionate about?
23. How do you keep up to date on the latest Computer news?
24. When did you become interested in computer software/hardware?
25. Have you ever disagreed with a manager’s decision, and how did you approach the disagreement? Give a specific example and explain how you rectified this disagreement, what the final outcome was, and how that individual would describe you today.
26. Describe a humbling experience.
27. What would you want to do 5 years from now?
28. What would you do if you encountered an engineering problem that is above your level of understanding?

## Theoretical

29. Assuming you are in a glass elevator, how would you determine how far you have traveled?
    1. Now assume that you are in a non-transparent elevator.

30. Assume you are in a boat in a small lake, what happens if you take the anchor out of the boat and drop it into the lake.

## Computer Science and Engineering Questions

- If you have 2 eggs, and you want to figure out what’s the highest floor from which you can drop the egg without breaking it, how would you do it? What’s the optimal solution?
- Assuming you have a bit array how would you count? $b_{N}\ldots\:b_{1}$, where N = 64
    - The leading/trailing ones 
    - Total ones
- You have a bit array; how would you count the number of ones in range $b_{N}\ldots\:b_{1}$ , where N = 64 $[k,\:l]$
- How would you design a blinking LED using a deterministic finite automata aka state machine?
- How would you reverse a singly linked list I.E. A->B->C->D, where each element has unique content and next element. The first element is marked as root and the last element points to nil delimiter.
- How would you find the Greatest Common divisor (GCD) and Least Common Multiple (LCM)? Hint: GCD of two integers is the largest positive integer that divides both numbers without remainder.
- What is the difference between a preemptive and a cooperative operating system? 
- What are the key elements in a consumer and producer model? 
- Given N elements determine the fastest method to achieve the mean then use that to determine the best run time computation Given N elements determine the fastest method to achieve the mean then use that to determine the best run time computation
- What is Big-O, Theta, and Omega mean?
- What is the difference between P and NP?
- How do you convert binary numbers to base 10?
- What is a proof direct, induction, contradiction proof?
- Draw a 3 by 3 grid. How many edges exist? Now do it for an N by M grid.
- Prove a tree with n nodes has n-1 edges. 
- What is the runtime of the following code?

    ```pseudocode
    for i = 1 to n
        for j = 1 to i
        k = I / j
    ```

- Provide the recurrence relation for all Fibonacci numbers 0, 1, 1, 2, 3, 5, 8, ...
-  What does the following Dynamic programing algorithm do?

    ```pseudocode
    f(int n) {
        if (n <= 2)
            A[n]= n;
        if(A[n] > 0)
            return A[n];
        else
            A[n] = f(n-1) + f(n-2);
        return A[n];
    }
    ```

- Provide the generic cost equations of a pipelined processor vs a non-pipelined. 53. What is the difference between CISC and RISC processor?
- What is the difference between a micro controller, vector, and super scalar processor?
    - 55. In floating point mathematics what happens when you add a number and $2^{64}$ and $2^{-32}$?
- What are the complications of the two functions when he high level function only has access to these generators?
    - $F(n) = A + 1$
    - $G(n) = A - 2$
- What is the difference between the Von Neumann architecture and Harvard architecture?
-  What is the difference between a Mealy and Moore state machine?
-  How would you write an regular expression checker so for every “(“ you insert a “)”?
