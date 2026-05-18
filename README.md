# minishell — UNIX Shell in C

> 42 Urduliz — Common Core project

A fully functional **UNIX command-line interpreter** built from scratch in C, replicating the core behavior of `bash`.

---

## Features

- **Command execution**: absolute path, relative path, and `PATH`-based lookup
- **Built-ins**: `echo`, `cd`, `pwd`, `export`, `unset`, `env`, `exit`
- **Pipes**: multi-stage pipelines (`cmd1 | cmd2 | cmd3`)
- **Redirections**: `<`, `>`, `>>`, `<<` (heredoc)
- **Environment variables**: full `$VAR` expansion and `$?` exit status
- **Signal handling**: `Ctrl+C`, `Ctrl+D`, `Ctrl+\` behave as in bash
- **Quote handling**: single and double quotes with correct expansion rules

## Build & Run

```bash
make
./minishell
```

## Project Structure

```
minishell/
├── main/
│   ├── minishell.c     # Entry point, REPL loop
│   └── signals.c       # Signal handlers
├── parsing/            # Lexer and token tree builder
├── token/              # Token type handling
├── exec/               # Command execution, pipes, redirections
├── builtins/           # Built-in command implementations
├── libft/              # Custom C library
├── minishell.h         # Shared header
└── Makefile
```

## Technical Highlights

| | |
|---|---|
| Execution | `fork()` / `execve()` / `waitpid()` |
| Pipes | `pipe()` + file descriptor management |
| Signals | `sigaction()` — context-aware handling |
| Memory | No leaks on all paths (Valgrind verified) |

## Skills

`C` `Process Management` `UNIX Signals` `Pipes` `Memory Management` `Parsing` `Linux`

---

## Academic Integrity

This repository is shared for **educational and portfolio purposes only**.

**For 42 students:**
- Do not copy this code for your own project submissions
- Use it as a reference to understand concepts and approaches
- Write your own original solution — that is the only way to actually learn

*42's core values are learning through practice, peer collaboration, and genuine problem-solving.*

---

## License

MIT — see [LICENSE](LICENSE) for details.
Copyright (c) 2026 Eneko Muñoz Bordona