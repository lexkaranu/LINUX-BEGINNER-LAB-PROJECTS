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

