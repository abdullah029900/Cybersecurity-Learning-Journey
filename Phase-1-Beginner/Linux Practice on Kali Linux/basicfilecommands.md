# Kali Linux Learning Journey 🐉

A hands-on documentation of my Kali Linux learning path, focused on building a strong foundation for cybersecurity and ethical hacking.

---

## About This Repository

This folder tracks my practical Kali Linux journey — from the very first command typed in a terminal to progressively advanced cybersecurity concepts. Every folder and file here represents real practice, real mistakes, and real progress.

**Goal:** Build strong Linux fundamentals before moving into penetration testing and ethical hacking.

---

## Current Status

| Phase | Topic                        | Status     |
| ----- | ---------------------------- | ---------- |
| 01    | Linux File System Theory     | ✅ Done    |
| 02    | File & Directory Management  | ✅ Done    |
| 03    | File Permissions & Ownership | 🔄 Up Next |
| 04    | User & Group Management      | ⏳ Pending |
| 05    | Networking Commands          | ⏳ Pending |
| 06    | Process Management           | ⏳ Pending |
| 07    | Bash Scripting Basics        | ⏳ Pending |
| 08    | TryHackMe Rooms              | ⏳ Pending |

---

## Phase 02 — File & Directory Management

### `touch`

Creates an empty file. If the file already exists, it updates the timestamp.

```bash
touch practice.txt          # creates a single file
touch song{1..5}.mp3        # creates song1.mp3 to song5.mp3 in one command
touch file{6..10}.txt       # creates file6.txt to file10.txt
```

---

### `mkdir`

Creates a new directory. Can create multiple directories in one command.

```bash
mkdir songs                 # creates a single directory
mkdir songs file            # creates two directories at once
mkdir sample                # creates a subdirectory inside current location
```

---

### `ls`

Lists files and directories in the current location.

```bash
ls                          # basic list
ls -l                       # detailed list with permissions, size, and timestamps
```

The `-l` flag is important — it shows file permissions, owner, size, and last modified time. Essential for understanding file system security.

---

### `cd`

Navigates between directories.

```bash
cd Desktop                  # move into Desktop
cd ..                       # go back one level (note: space required between cd and ..)
cd ~/Desktop/songs          # navigate using full path
```

> ⚠️ Common mistake: `cd..` throws "command not found". Always use `cd ..` with a space.

---

### `file`

Identifies the actual type of a file — regardless of its extension.

```bash
file song1.mp3              # returns: empty (because the file has no real content)
file file10.txt             # returns: ASCII text (after writing content into it)
```

> 🔍 Key discovery: Linux does not trust file extensions. It reads the actual file content to determine what a file really is. This has direct implications in cybersecurity — attackers can rename malicious files with innocent extensions. The `file` command sees through that.

---

### `cat`

Reads and displays file content. Also used to write content into a file.

```bash
cat file10.txt              # displays file content
cat > file10.txt            # writes into file (press Ctrl+C to save and exit)
cat text11.txt              # throws error if file doesn't exist
```

> ⚠️ Common mistake: `cat > text11.text` creates `text11.text`, not `text11.txt`. Always double-check your extension when typing.

---

### `cp`

Copies a file from one location to another.

```bash
cp file6.txt sample/        # copies file6.txt into the sample directory
```

---

### `rm`

Deletes a file permanently. No recycle bin in Linux.

```bash
rm file10.txt               # deletes file10.txt
rm song1.mp3                # deletes song1.mp3
```

> ⚠️ There is no undo. Once deleted, the file is gone.

---

### `touch -am`

Updates both the access time and modification time of an existing file to the current time.

```bash
touch -am file10.txt        # updates timestamp of file10.txt
```

Useful for understanding how Linux tracks file activity — relevant in forensics and log analysis.

---

## Key Discoveries So Far

- **Linux ignores file extensions.** The `file` command reveals what a file truly is. A `.mp3` file with no audio data returns `empty`, not `audio`.
- **`cd..` is not a command.** The space in `cd ..` is mandatory — a small but important habit to build.
- **`cat >` overwrites.** Writing to an existing file with `cat >` replaces all previous content. Use `cat >>` to append instead.
- **Typos in filenames matter.** Creating `text11.text` instead of `text11.txt` is a real file with a different name — Linux will not correct you.

---

## Open Questions

- If Linux doesn't trust file extensions, how do attackers use this to disguise malicious files?
- How does `file` determine file type internally — magic bytes?
- What happens to file permissions when you `cp` vs `mv` a file?

---

## Tools & Environment

- **OS:** Kali Linux (VMware Workstation)
- **Platform:** TryHackMe
- **Hardware:** Dell Laptop

---

## Connect

- **LinkedIn:** [Abdullah Abbasi](https://www.linkedin.com/in/abdullah-abbasi-38775635b/)
- **GitHub:** [24pwbcs1319-glitch](https://github.com/24pwbcs1319-glitch)
