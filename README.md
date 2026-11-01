# Reverse Vibe Coding Platform Services

This repo exists entirely to demonstrate ability to handwrite code and experiment with "reverse vibecoding"

Rules of Game
- I tell the LLM what sort of spec to write.
- I write the code by hand to match the spec and tickets

LLM writes tickets
- The LLM splits spec into tickets (does work of Project Owner or Project Manager)
- LLM can write code to create tickets, issues, etc (see `spec/src`)
- LLM can write github issues and update the project board.
- Tickets can have application interface (external contracts, not internal interfaces) but otherwise no code samples
- LLM shall not write the unit tests as spec

I can use linters, google search, or as LLM questions
- Linters and all tooling is fair game
- All questions to LLM will be logged in questions in `/questions/QUESTION_LOG.md`
- All google searches will be logged to `/searches/SEARCH_LOG.md`

I think historically maybe 1 out 20 job leads involve someone that looks at my code portfolio.

Thank you for being part of the 5% and evaluating candidates on code.