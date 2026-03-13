# Task1 Findings

### First Issue commit 2ee27fac6803b9010fb5fb0393b0bd6fa27ddaab
Updating README.md, config.txt, and notes.txt in a single commit is not a good approach.
These are unrelated changes that should have been separate commits to keep understanding clean.

### Second Issue commit f6cd2274dc58b363d901c6b1dc294e43f4aef296
This commit introduced secrets.txt containing a hardcoded API key. 
First adding secret keys and wallet addresses to the server is very dangerous for data leak and hacking attack.
Also, the message disguised it as a config file, not a secrets file Which is more difficult to identify.

### Third issue commit 4a0530fbace2d5d73b9a36ee8ae29a941634178e
This commit added a stray line in todo.txt I think.
"This line should not be here - it was added by mistake."
It ambiguous that it should be removed or kept if it is a mistake.