# Minishell

Minishell is a custom shell program developed in C that replicates the basic functionalities of a Unix shell. This project demonstrates command-line interface design, handling of shell features, and implementation of essential built-ins.

## Features

- **Prompt Display:** Shows a command prompt and waits for user input.
- **Command Execution:** Executes commands with support for:
  - Redirections: `<` (input), `>` (output), `<<` (here document), `>>` (append)
  - Pipes: `|` (connects the output of one command to the input of the next)
- **Command History:** Maintains a history of commands for navigation and re-execution.
- **Quoting:** Handles single (`'`) and double (`"`) quotes to manage meta-characters and environment variable expansion.
- **Environment Variables:** Expands environment variables (e.g., `$HOME`) and special variables like `$?` for exit status.
- **Built-ins:** Implements essential shell built-in commands:
  - `echo` with `-n` option
  - `cd` for changing directories
  - `pwd` to print the current working directory
  - `export` to set environment variables
  - `unset` to remove environment variables
  - `env` to display environment variables
  - `exit` to exit the shell
- **Signal Handling:** Manages signals (`ctrl-C`, `ctrl-D`, `ctrl-\`) with appropriate behavior:
  - `ctrl-C` displays a new prompt on a new line.
  - `ctrl-D` exits the shell.
  - `ctrl-\` does nothing.

## Requirements

- **Libraries:** Uses standard Unix libraries and functions, including `readline`, `execve`, `pipe`, `fork`, and others.
- **System Calls:** Utilizes various system calls for process management, file operations, and signal handling.

## Building

To build the project, use the provided `Makefile`. The following targets are available:

- `make all`: Build the shell executable.
- `make clean`: Remove object files and temporary files.
- `make fclean`: Remove all files including the shell executable.
- `make re`: Rebuild the project.

```sh
make all
Usage

To run the shell:

sh

./minishell

The shell will display a prompt and wait for user commands. You can use built-ins, execute external commands, and use redirections and pipes as described in the features section.
Examples

    Running a command with output redirection:

    sh

echo "Hello, World!" > output.txt

Running a pipeline:

sh

    ls -l | grep "txt"

Notes

    Ensure that the readline library is installed on your system as it is used for handling input and command history.
    This shell is intended for educational purposes and may not handle all edge cases or provide all functionalities of a full-featured shell like Bash.

License

This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgements

    Developed as part of a software engineering course or personal project.
    Inspired by standard Unix shell implementations.

Feel free to adjust the sections as needed to better fit your project specifics or preferences!
