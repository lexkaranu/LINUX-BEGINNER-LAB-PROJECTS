THIS IS AN OVERVIEW OF ALL PROJECTS
 
 1. File Permissions Mini Lab

## Goal
Learn how file permissions work on Linux using chmod.

## Steps

```bash
# Step 1: Create file
touch example.txt

# Step 2: View current permissions
ls -l example.txt
# Output:
# -rw-r--r-- 1 user user 0 Aug 2 10:00 example.txt

# Step 3: Change permissions to read-only
chmod 444 example.txt

# Step 4: Try writing to the file
echo "test" > example.txt
# Output:
# bash: example.txt: Permission denied

2.SIMPLE PORTSCANNER


 **Goal**:

To scan ports 20–80 on your local machine (`127.0.0.1`) and display which ones are open.



 **Tools used**:

* `nano` (to create the file)
* `chmod` (to make the script executable)
* `nc` / `netcat` (for scanning ports)
* `bash` (to run the script)

 **Step-by-Step Instructions**


### **1. Open a terminal in LabEx**

You’re working in a browser-based Linux shell.

### **2. Create a new script file with `nano`**

USE COMMAND;
nano portscan.sh

This opens the nano text editor.


### **3. Paste the script into the file**


#!/bin/bash
for port in {20..80}
do
  nc -zv 127.0.0.1 $port 2>&1 | grep succeeded
done


This script scans ports from 20 to 80 on `localhost`.

---

### **4. Save and exit nano**

* Press `CTRL + O`, then `Enter` to save the file.
* Press `CTRL + X` to exit nano.

---

### **5. Make the script executable**

```bash
chmod +x portscan.sh
```

This lets you run the file like a program.


### **6. Run the script**

```bash
./portscan.sh
```

This will scan ports and display results for open ones.

---

### ✅ **Optional: Test an open port**

If no ports seem open, start a temporary web server:

```bash
python3 -m http.server 80
```

Then re-run:

```bash
./portscan.sh
```

Now port 80 should show as open:

```
Connection to 127.0.0.1 port 80 [tcp/http] succeeded!
```


