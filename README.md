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
