
## Viewing Files

Linux provides several commands to view file contents directly from the terminal without opening a full editor.

### more

The `more` command displays file content one screen at a time. It is useful for viewing long files.

- Press **Space** to go to the next page.
    
- Press **q** to quit.
    

Example:  
`more file.txt`

---

### less

The `less` command is an improved version of `more`. It allows forward and backward navigation in a file.

- Use **Arrow keys** to scroll.
    
- Press **q** to quit.
    

Example:  
`less file.txt`

---

### head

The `head` command shows the first 10 lines of a file by default.  
Example:  
`head file.txt`

To display a specific number of lines:  
`head -n 5 file.txt`

---

### tail

The `tail` command shows the last 10 lines of a file by default.  
Example:  
`tail file.txt`

To monitor a file in real time (useful for logs):  
`tail -f file.txt`

---

# Filtering Text

Linux provides powerful tools to filter and extract specific data from files.

### Cut

The `cut` command extracts specific columns or fields from a file. It is often used with structured data.  
Example (extract first column using space delimiter):  
`cut -d " " -f1 file.txt`

- `-d` → delimiter
    
- `-f` → field number
    

---

### Word Count (wc)

The `wc` command counts lines, words, and characters in a file.  
Example:  
`wc file.txt`

Options:

- `wc -l` → count lines
    
- `wc -w` → count words
    
- `wc -c` → count characters
    

---

# File Descriptors and Redirections

## File Descriptors

In Linux, everything is treated as a file, including input and output. There are three standard file descriptors:

- `0` → Standard Input (stdin)
    
- `1` → Standard Output (stdout)
    
- `2` → Standard Error (stderr)
    

These control how data flows in and out of commands.

---

## Redirections

Redirection allows you to change where output goes or where input comes from.

- `>` → Redirect output (overwrite file)  
    Example: `echo Hello > file.txt`
    
- `>>` → Append output to a file  
    Example: `echo World >> file.txt`
    
- `<` → Take input from a file  
    Example: `wc -l < file.txt`
    
- `2>` → Redirect error messages  
    Example: `command 2> error.txt`
    

---

## Pipes

A pipe (`|`) sends the output of one command directly as input to another command.

Example:  
`cat file.txt | grep "hello"`

This sends the content of `file.txt` to `grep` to search for the word "hello".

Pipes are very powerful and allow you to combine multiple commands together.

---

# Regular Expressions

Regular expressions (regex) are patterns used to search for specific text. They are commonly used with commands like `grep`, `sed`, and `awk`.

Common regex symbols:

- `.` → Any single character
    
- `*` → Zero or more occurrences
    
- `^` → Beginning of a line
    
- `$` → End of a line
    
- `[abc]` → Matches a, b, or c
    
- `[^abc]` → Matches any character except a, b, or c
    

Example:  
`grep "^root" file.txt`

This searches for lines that start with the word "root".

Regular expressions make text searching and filtering in Linux extremely powerful and flexible.