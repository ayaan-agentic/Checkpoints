<img width="1280" height="640" alt="image" src="https://github.com/user-attachments/assets/a0b7c6ba-bfca-45ac-9f6f-c7dbbda78d44" />
# Checkpoints

been thinking about a problem I keep running into with coding agents 

they get 95% through a big task… then hit the context limit, usage cap, or timeout. and you’re left with half-edited files, a broken build, and no idea what the agent was thinking.

so I’m sketching an idea called Checkpoints: a small open protocol where agents treat running out of budget as an expected event, not a crash.

the gist:

agent reserves the last ~5-10% of its budget
when it hits that line, it stops starting new work, stabilizes the repo, runs quick validation, and writes down what’s done, what’s left, and why it made the calls it did
the next agent (or you) reads the checkpoint, verifies the repo matches, and picks up from next_action

plus lightweight checkpoints along the way, so a hard crash only costs you the last step.

does this solve something you actually hit, or is it overthinking it? honest takes welcome 🙏
