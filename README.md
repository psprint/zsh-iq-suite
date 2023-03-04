# Zsh Angel IQ System

A bunch of intelligent extensions to Zsh. Features:

1. Smart console – a TUI application allowing to run configure & make
   and open editor on exact locations of reported errors.
2. In-shell Ctags browser – list all symbols in `TAGS` index created
   with Universal Ctags and open editor on their source locations.
3. Angel Swiss Knife – a utility allowing:
   - quick Ctags generation,
   - variable contents dumping,
   - swapping 2 files' locations,
   - repository creating on GitHub,
   - hopping – spawning blocks of code to call back in command line after
     specified time,
   - escape codes (for colors, etc.) filter – works either on stdin or
     on commandline arguments,
   - `try-ng` – takes string and a pattern and returns the result. NON-GREEDY mode"
   - `tries-ng` – takes strings and a pattern and returns the strings each after pat applied. NON-GREEDY mode
   - `try` – the same as `try-ng`, but greedy
   - `tries` — the same as `tries-ng`, but greedy
   - `x-tract` — extracts any archive, recognizes many types
 

3. An extension to Zinit plugin manager – *action complete* – press
   `Alt-a` to complete a name of plugin and `Alt-c` to complete
   a name of ice modifier.
4. A set of global aliases in the form `NAME…STR` allowing clever
   tests of variable contents. The strings are:
   - `EMPTYSTR` – `[:space:][:INCOMPLETE:][:INVALID:]$'\e']#` – any
     number of spaces, incomplete chars or invalid chars –
     essentially an empty string,
   - `INVALIDSTR` – `*[[:INCOMPLETE:][:INVALID:]]*` – a string
     holding at least one invalid character,
   - `EMORINSTR` – empty or invalid string,
   - `FUNCSTR` – a string of the form: `abc() {…` with all possible
     variants (like e.g.: preceding `function` keyword),
   - `IDSTR` – a string with all characters allowed in Zsh variable
     name,
   - `PRINTSTR` – a string with all characters being printable,
   - `WRONGSTR` – a string either empty, invalid, control-chars only,
     zeroes-only or non-printable only,
   - `ZEROSTR` – a string with only `0` character,
   - `CTRLSTR` – a string consisting of only control characters.

To use the global alias do:
```zsh
if [[ $var == WRONGSTR ]]; then
…
fi
```

## Build console

A TUI frontend to `configure` and `make`. Its main feature is
opening `$EDITOR` on exact position of an error or warning in its
source file.

![Angelcon](https://raw.githubusercontent.com/psprint/zsh-angel-system/master/share/img/angelcon.png)

## Ctags browser

A in-shell Ctags symbol browser, under the prompt (`alt-w` to activate):

![symbrowse](https://raw.githubusercontent.com/psprint/zsh-angel-system/master/share/img/symbolbrowse.png)
**
## Usage information
Below are subcommands of the command `angel`, i,e,L `angel {subcommand} …`

- **tags** : generate Ctags for current directory
- **con** : open smart console for current directory
- **filter** : filters out any color escape codes, reads stdin if no arguments
- **fresh-in** : finds files changed in ARGUMENT-minutes
- **gh-create** : create a repository at GitHub
- **hop** : deploy a block of code for later execution in ZLE-scope
- **qprint** : print contents of given variable (by name not by value)
- **swap** : swap two files in their locations
- **tries** : the same as tries-ng, but greedy
- **tries-ng** : takes strings and a pattern and returns the strings each after the pattern applied. NON-GREEDY mode
- **try** : the same as try-ng, but greedy
- **try-ng** : takes string and a pattern and returns the matched string. NON-GREEDY mode
- **x-tract** : extracts any archive, recognizes many types
