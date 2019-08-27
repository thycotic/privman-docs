[title]: # (How to Meet FISMA)
[tags]: # (read me)
[priority]: # (80002)
# How to Meet FISMA Compliance in 9 Steps

Any organization that maintains a computer network is vulnerable to outside attacks.  Even if it is a single computer in someone's home, break-in attempts are constant with hackers automatically pinging addresses (including your home router) looking for cracks they can sneak through.  At home, it's bad enough that the exposure is your personal data including family photos, bank, and financial information and other personal information.  Now, apply that to the federal government, the FBI, IRS, DoD, etc.  The data here obviously needs to be protected.  If something is stolen and leaked there, it could be devastating.

If you work in security for the federal government or have any dealings with computer systems for any government agency, you know there are policies in place to generally protect systems across the board. No matter if they are a PoS (point of sale) system, web server, mail server, or servers housing top secret data.  The high-level compliance driver today for the federal government is something called FISMA, or the Federal Information Security Management Act guidelines. FISMA is United States legislation that defines a comprehensive framework to protect government information, operations and assets against natural or man-made threats.  FISMA assigns responsibilities to various agencies to ensure the security of data in the federal government. The act requires program officials, and the head of each agency, to conduct annual reviews of information security programs, with the intent of keeping risks at or below specified acceptable levels in a cost-effective, timely, and efficient manner.

The National Institute of Standards and Technology (NIST) outlines nine steps toward FISMA compliance:

1. Categorize the information to be protected.
2. Select minimum baseline controls.
3. Refine controls using a risk assessment procedure.
4. Document the controls in the system security plan.
5. Implement security controls in appropriate information systems.
6. Assess the effectiveness of the security controls once they have been implemented.
7. Determine agency-level risk to the mission or business case.
8. Authorize the information system for processing.
9. Monitor the security controls on a continuous basis.
(http://searchsecurity.techtarget.com/definition/Federal-Information-Security-Management-Act)

Here are some common sense approaches you can apply to meet not only some of these requirements, but other standards found across the computer industry.

What do you need to protect?  Most data and other security assets can only be accessed using a privileged account, so it makes sense to start there.  We recommend protecting privileged access across the enterprise and lock down Windows endpoints to prevent a hacker's ability to get access to privileged accounts.  We do note it does not necessarily prevent hackers from getting in, but we protect valuable computer assets from a hacker when they compromise the perimeter – because there is a high probability they will.  It's not a question of if, it's a question of when, and how many times.  And we are not just talking about external hackers and threats – we are talking about internal threats as well.

The Thycotic approach

To simplify our approach at Thycotic, here is what we do:

1. Discover accounts on computer assets (workstations, server, switches, routers, *NIX systems)
2. Identify (on Windows systems) which of those accounts have administrative rights. These are the accounts you need to control access to because this is what hackers are looking to compromise.
3. Remove administrative rights from day-to-day users. Keep all ‘regular' users in STANDARD USER CONTEXT.
4. Control access to those administrative accounts that remain.
5. Discover what applications require administrative rights – if you don't know already.
6. Apply application controls around all processes/programs/executables/installers run by both end users and administrative users.
   a. Including the ability to protect systems from the unknown by applying real-time application analysis to protect against zero-day attacks ransomware and other malicious software.

With this approach, you can keep the bad guys away from your data, and keep them (or anyone else using an email attachment, or a browser session, etc.) from running bad things on your computers – workstations or servers, real or virtual.

If you can do all of this, and provide a centralized place to manage all of it – AND provide (in that same centralized location) the ability to create nice audit reports around all of this security management, you are well on your way in meeting compliance. Compliance is not only FISMA, but for other standards as well.

Privileged Manager for Windows applies application control policies to both workstations and servers to control what a user or an administrator can run on the endpoint.

Compliance is mostly about common sense. Once you read all of the small print included in the standards you need to follow, it really boils down to this:

* Control access to data and resources
* Provide backup and recovery mechanisms for your data
* Get everyone onboard to use the controls you put in place to protect your data
* Make sure you can prove your controls are working

Here at Thycotic, we can get you well on your way in putting compliance practices in place no matter the standards that govern you and your organization.
