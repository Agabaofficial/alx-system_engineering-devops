When I was working for SlideShare, I worked on an auto-remediation tool called Skynet that monitored, scaled and fixed Cloud infrastructure. I was using a parallel job-execution system called MCollective that allowed me to execute commands to one or multiple servers at the same time. I could apply an action to a selected set of servers by applying a filter such as the s hostname or any other metadata we had (server type, server 
There were 2 pieces of bad news:

When MCollective receives nil as an argument for its filter method, it takes this to all 
The action I sent was to terminate the selected servers
I started the parallel job-execution and after some time, I realized that it was taking longer than expected. Looking at logs I realized that I was shutting down s entire document conversion environment. Actually, 75% of all our conversion infrastructure servers had been shut down, resulting in users not able to convert their PDFs, powerpoints, and videosSlideShareserversmean environmentserver