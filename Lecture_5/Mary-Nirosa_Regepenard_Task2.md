
# Lecture 5 – Task 2: Search and Filter

## Step 1: Change to the working directory

Command:
```bash
cd ~/shell-redirections
```

## Step 2: Search for processes belonging to my user

Command:
```bash
ps aux | grep mary-nirosa
```

Output:
The command searched for processes containing my username. The username was truncated in the process list, so the full username was not found.

## Step 3: Search using the truncated username

Command:
```bash
ps aux | grep 'mary-ni+'
```

Output:
The command displayed processes containing the truncated username, including systemd --user, sd-pam and bash. The grep process was also displayed.

## Step 4: Use a regular expression to match the username

Command:
```bash
ps aux | grep '^mary-ni[+][[:space:]]'
```

Output:
The command displayed processes whose username in the first column matched mary-ni+.

## Step 5: Display all processes except root

Command:
```bash
ps aux | grep -v '^root[[:space:]]'
```

Output:
The command excluded processes belonging to root and displayed processes belonging to other users.

## Step 6: Exclude kworker and irq processes

Command:
```bash
ps aux | grep -Ev '[k]worker|[i]rq'
```

Output:
The command excluded processes containing kworker or irq and displayed the remaining processes.
