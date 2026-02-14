## 1 Launch this command, then Record its Job ID cat /dev/zero > /dev/null &
cat /dev/zero > /dev/null &
jobs -1

jobs 

## 2 Use a single command to display detailed information about this process.
ps -f 13128

## 3 Save the full output of this command to a file named process_info.txt
ps -fp 13128 > process_info.txt

## 4 Change the priority of this cat process between 10 and 15
renice 12 -p 13128

## 5 Verify the change by displaying the process's new niceness value. Append this verification output to process_info.txt
ps -o pid,ni,cmd -p 13128 >> process_info.txt

cat process_info.txt

## 6 Terminate the original cat /dev/zero > /dev/null process using its PID.
kill 13128

## 7 Verify the process is no longer running.
ps -f 13128

