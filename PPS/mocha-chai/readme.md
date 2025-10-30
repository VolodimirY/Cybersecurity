# ☕🔍 Guía Introductoria a Mocha + Chai / Mocha + Chai Beginner’s Guide

**Mocha** and **Chai** form one of the most popular combinations for **automated JavaScript testing** within the **Node.js** environment.  

- 🧠 **Mocha** is the **testing framework** responsible for running and structuring tests, organizing them into logical blocks (`describe`, `it`, etc.).  
- ⚖️ **Chai** is an **assertion library** that helps verify whether the actual results match the expected ones, offering readable styles like `assert`, `expect`, or `should`.

Together, they allow developers to write **clear, expressive, and maintainable** tests, improving code quality and catching errors early in development.

### 📗 In this guide, you will learn how to:
- Install and configure **Mocha + Chai** in a **Node.js** project.  
- Understand the difference between **Mocha (test runner)** and **Chai (assertions)**.  
- Write and execute your first unit tests.  
- Read test outputs and handle errors effectively.  

🎯 **Goal:** By the end, you’ll be able to set up a professional testing environment to ensure your JavaScript applications run correctly.

---

First of all we need to download node and npm, you can check if its correctly installed by typing  `node -v; npm -v`

Once you got this, create a new folder and type `npm init`

<img width="684" height="471" alt="image" src="https://github.com/user-attachments/assets/7fe1f6d2-58cf-4920-9151-c43b14566302" />

Now we need to download *Mocha framework*  with this command `npm install mocha --save` and now we can find that two new files have been added. 

<img width="860" height="303" alt="image" src="https://github.com/user-attachments/assets/dab25b57-335e-4b31-afcf-dedcffe44aae" />

Now we got evetiching we needed, lets try to code something simple, like this 3 calculator functions. 

<img width="280" height="266" alt="image" src="https://github.com/user-attachments/assets/c17419cb-a277-4d3d-9c39-86c34b0e41ce" />

This is my configuration file, we need to specify the assert (chai) and the programm we are targeting (calculator2):

`var assert = require("chai").assert;`

`var calculator = require("../app/calculator2");`

<img width="554" height="321" alt="image" src="https://github.com/user-attachments/assets/2cd19334-9c1a-4e00-8ab1-1dadd434996a" />

