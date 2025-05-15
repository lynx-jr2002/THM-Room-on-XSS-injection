# THM-Room-on-XSS-injection

TryHackMe Room Report: Exploring Cross-Site Scripting (XSS)
1. Room Overview
 Title: XSS Playground: XSS 101
 Objective:
This room is designed to help learners understand and exploit various types of
Cross-Site Scripting vulnerabilities. Through simple scenarios, users will practice
identifying, exploiting, and mitigating XSS flaws in web applications.
 Key Vulnerabilities/Concepts Covered:
o Reflected XSS
o Stored XSS
o DOM-based XSS
o Bypassing filters
o Stealing data using malicious scripts
o Real-world implications and prevention strategies
2. Learning Objectives
Participants will:
 Understand the core concepts of XSS.
 Learn how to diƯerentiate between reflected, stored, and DOM-based XSS.
 Gain hands-on experience crafting payloads and exploiting XSS flaws.
 Learn how to use developer tools to inspect and manipulate JavaScript in the
browser.
 Discover how XSS can be used to exfiltrate cookies, steal data, or escalate
privileges.
3. Room Structure
 Section 1: Introduction to XSS
 Content:
1. Brief theory part (an introduction about XSS) with examples.
 Reflected XSS
 Stored XSS
 DOM based XSS
2. Questions from the introduction to test the knowledge.
 Outcome: Understand what XSS is and how it works.
Section 2: Introduction to Reflected XSS
 Challenge: Brief theory part about how it works, why it is called reflected XSS,
example scenario, common injection methods, risks and impact and mitigation with
an interactive quiz.
 Outcome: Understand what reflected XSS is and how it works and mitigation from
it.
Section 3: Reflected XSS Challenge (/ref-xss lab)
 Challenge: Exploit a search form that reflects user input. Hosted with apache using
reverse proxy. In the challenge search input is reflected onto the page but the server
would detect a successful payload and rewards the flag. Player must inject a
working JS payload to trigger the flag.
 There is no /getflag or other endpoint that would leak the flag. The flag is only
inserted into the rendered page after a successful XSS payload is detected inside
/search. Any other URL will hit 404 Not Found. No static folders served therefore
no directory traversal. No server file leaks since no public static directory. No source
code or manually guessed routed would show a flag since they are redirected to 404
error.
 Outcome: Learn how attackers craft payloads in URLs and how the browser
executes them. Players must inspect and discover the page around to spot the
response method and craft their payload.
Section 4: Introduction to Stored XSS
 Challenge: Brief theory part about how stored XSS works, an example scenario,
common targets for stored XSS attacks, risks and impacts mitigation methods and
in the end a table explaining the diƯerence between reflected XSS and stored XSS
with an interactive quiz.
 Outcome: Understand what reflected XSS is and how it works, mitigation.
Section 5: Stored XSS (/str-xss lab)
 Challenge: Posts a malicious script in a comment box that gets executed when
another user views it. The player will practice through crafting and exploiting a
stored XSS by injecting a JS code inside the comment box so that it automatically
fetches and displays the hidden flag from the server.
 However, player cannot access /get-flag and must build a working JS payload to
retrieve the flag. There are hidden hints in the page source, player has to take them
into consideration when crafting the flag.
 Outcome: Learn how to inspect the source and adhere given details and create a
simple stored XSS payload.
Section 6: Introduction to DOM based XSS
 Challenge: Brief theory part about DOM based XSS, how DOM based XSSS works,
an example scenario, common targets for DOM based XSS, payload examples,
mitigation methods with an interactive quiz.
 Outcome: Understand what reflected XSS is and how it works, mitigation.
Section 7: DOM-based XSS (/dom-xss lab)
 Challenge: Manipulate URL fragments to trigger an alert or steal data. Unlike
traditional reflected and stored XSS, in this challenge player has to explore clientside injection vulnerabilities where the server is not directly responsible for
reflecting malicious code, but the javascript on the page is.
 Player must craft a payload after carefully inspecting the page source and bypass
the security.
 Direct access to /get-flag, curl, wget or other manual methods, directory traversal
are blocked, and a java script injection point only exist in DOM where the flag is only
accessible through an XSS attack.
 Outcome: Learn client-side vulnerabilities not involving the server.
Section 7: Bonus Challenge 1(/bonus)
 Challenge: to exploit a DOM-based XSS vulnerability that does not have proper
sanitization. If the injected input includes a script (<script>) or image with onerror, it
gets executed. Once the script executes, it can call showFlag() to fetch the flag.
 Player has to craft a JS payload through the hash function of the URL that trigger an
exaction and calls showFlag() function.
 Outcome: Gets additional hands on experience about DOM based vulnerabilities.
Section 9: Bonus Challenge 2 (/bonus2)
 Challenge: Create a payload to steal the flag. Inputs are sanitized so the player
must be considerate to choose a hidden backdoor by exploiting a custom javascript
logic path(eval(runJS=...)). Strong access controls are applied to the server file. The
player must create a malicious URL to reveal the hidden flag.
 Considering the attack vector, all the direct flag access, directory traversal, basic
<script> injection and non-browser tools like curl are blocked.
 Outcome: Learns how to craft a payload avoiding weak mitigation methods.
Section 10: Bonus Challenge 3 (/bonus3)
 Challenge: create a payload to exploit a hidden JS function (hiddenFlagFunction())
using a crafted name parameter in the URL. Sanitization layers added so the player
must create an exploit that bypass them by inspecting the source code. All the angle
brackets and double quotes are encoded.
 When it comes to the security vectors, direct flag access, directory traversal, basic
XSS and tool based access are blocked and the main attack vector is considered to
be logic injection via execute method.
 Outcome: Learns how to inspect the source code and d craft a payload avoiding
sanitization methods.
4. Room Link
 TryHackMe Room (Draft) - https://tryhackme.com/jr/lynx22
5. Reflection
 Personal Insights:
o Designing this room helped me deepen my understanding of XSS beyond the
theoretical level. Creating realistic scenarios and configuring services
(Node.js, Apache, Docker) gave me a full-stack appreciation of how security
vulnerabilities are introduced and exploited. Even though it was unable to
host in the attack box, details are given for players to host it on their own
using docker on a virtual machine.
o When mentioning my experience, since I was not familiarized with tryhackme
attackboxes and how the virtual machine we upload in the room works in the
attackbox - when we upload a custom VM to an tryhackme room, it becomes
isolated, cloud based instance that players can deploy and interact through
their attackbox, I created my project first using docker and since that did not
work I hosted using apache reverse proxy.
But since there are port restrictions, the ports I set became unavailable in the
attackbox and docker containers did not run since services may not start
automatically in the attackbox therefore I had to create the project from
scratch to host the site on localhost with apache even then the attackbox
failed.
 Lessons Learned:
o Managing services inside virtual environments can be complex (e.g., port
conflicts, Apache/Node integration).
o Using PM2 and Docker simplifies service management and persistence.
o It's important to guide users step-by-step when labs involve external tools or
headers (like custom header-based flag access).
 Contribution to the Community:
This room oƯers practical, modular, and reusable labs for learners of all levels. It
complements existing TryHackMe content while allowing instructors to tailor their
approach or use parts of it in CTFs or security training. 
