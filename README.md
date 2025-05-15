# THM-Room-on-XSS-injection

1. Room Overview
Title: XSS Playground: XSS 101

Objective:
This room is designed to help learners understand and exploit various types of Cross-Site Scripting (XSS) vulnerabilities. Through simple and practical scenarios, users will practice identifying, exploiting, and mitigating XSS flaws in web applications.

Key Vulnerabilities/Concepts Covered:

Reflected XSS

Stored XSS

DOM-based XSS

Bypassing filters

Stealing data using malicious scripts

Real-world implications and prevention strategies

2. Learning Objectives
Participants will:

Understand the core concepts of XSS.

Learn how to differentiate between Reflected, Stored, and DOM-based XSS.

Gain hands-on experience crafting payloads and exploiting XSS flaws.

Use browser developer tools to inspect and manipulate JavaScript.

Discover how XSS can be used to exfiltrate cookies, steal data, or escalate privileges.

3. Room Structure
Section 1: Introduction to XSS
Content:

Brief theory with examples:

Reflected XSS

Stored XSS

DOM-based XSS

Knowledge-check questions

Outcome: Basic understanding of XSS and its types.

Section 2: Introduction to Reflected XSS
Challenge:
Theoretical overview with quiz covering how reflected XSS works, common attack vectors, and mitigation techniques.

Outcome: Learn about reflected XSS mechanics and defense.

Section 3: Reflected XSS Challenge (/ref-xss)
Challenge:
Exploit a vulnerable search form. The server detects a successful payload and reveals the flag only if executed correctly. No flag is leaked via endpoints like /getflag. All non-XSS paths lead to 404 Not Found.

Outcome: Learn to identify and exploit reflected XSS through crafted URLs and browser behavior.

Section 4: Introduction to Stored XSS
Challenge:
Theory with an interactive quiz explaining how stored XSS works and mitigation strategies.

Outcome: Understanding persistent attack vectors and storage-based scripting attacks.

Section 5: Stored XSS Challenge (/str-xss)
Challenge:
Inject JavaScript in a comment box to trigger script execution for another user. The flag is fetched using an injected script—direct access to /get-flag is blocked.

Outcome: Learn to craft stored XSS payloads and use browser inspection tools.

Section 6: Introduction to DOM-based XSS
Challenge:
Overview with quiz explaining DOM-based XSS, where the vulnerability lies in client-side JavaScript.

Outcome: Learn the difference between server-side and client-side XSS.

Section 7: DOM-based XSS Challenge (/dom-xss)
Challenge:
Manipulate the URL fragment to inject code. The flag can only be retrieved through DOM injection, not through direct requests or tools like curl.

Outcome: Understand and exploit DOM-based client-side JavaScript vulnerabilities.

Section 8: Bonus Challenge 1 (/bonus)
Challenge:
Exploit a DOM-based XSS via location.hash. Use <script> or image onerror injection to call a showFlag() function.

Outcome: Reinforce DOM XSS concepts through custom JavaScript behavior.

Section 9: Bonus Challenge 2 (/bonus2)
Challenge:
Bypass strong sanitization using eval(runJS=...) backdoor logic. Common injection techniques are blocked.

Outcome: Learn advanced payload crafting and bypass logic.

Section 10: Bonus Challenge 3 (/bonus3)
Challenge:
Inject into a name parameter to trigger hiddenFlagFunction() despite angle brackets and double quotes being encoded. Direct methods and tools are blocked.

Outcome: Practice bypassing sanitization using JavaScript logic inspection.

4. Room Link
TryHackMe Room (Draft): https://tryhackme.com/jr/lynx22

5. Reflection
Personal Insights:
Designing this room helped me deepen my understanding of XSS beyond theory.

Creating realistic scenarios and configuring Node.js, Apache, and Docker gave me full-stack insight into how web vulnerabilities occur.

Initially, I tried to use Docker and PM2 for hosting, but the attackbox had port and service limitations.

I later switched to hosting with Apache reverse proxy, but due to how TryHackMe handles uploaded VMs, services didn't behave as expected.

Ultimately, the labs are designed to be hosted locally using Docker or Apache with clear instructions.

Lessons Learned:
Hosting services inside virtual machines comes with challenges (e.g., port conflicts, startup dependencies).

Docker and PM2 are excellent for local testing but may not translate well to TryHackMe's attackbox environment without extra configuration.

Step-by-step instructions and troubleshooting tips are essential for user experience.

Contribution to the Community:
This room offers practical, modular, and reusable XSS labs suitable for all learning levels.

Instructors can reuse individual challenges in CTFs or training.

The challenges combine theory, hands-on application, and real-world attack simulation in a safe environment.
This room oƯers practical, modular, and reusable labs for learners of all levels. It
complements existing TryHackMe content while allowing instructors to tailor their
approach or use parts of it in CTFs or security training. 
