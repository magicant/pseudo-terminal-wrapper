# pseudo-terminal-wrapper (ptwrap)

This is a simple tool that runs a command in a pseudo-terminal as a demonstration of how to use pseudo-terminals.

1. Open a new pseudo-terminal.
1. Create a new child process and move it into a new session, in which the command is executed with its stdin/out/err connected to the slave side of the pseudo-terminal.
1. Turn the original terminal into the non-canonical input mode so that any input to the original terminal can be passed without delay or modification.
1. Forward all input and output between the original terminal and the master side of the pseudo-terminal.
1. Change the window size of the pseudo-terminal accordingly when that of the original terminal is changed.
1. Receive the exit status from the child process and return it as that of the wrapper itself.

## Requirements

- C99 compiler
- POSIX.1-2001 C API with XSI conformance

## Usage

```
ptwrap <command> [<argument>...]
```

## License

MIT
