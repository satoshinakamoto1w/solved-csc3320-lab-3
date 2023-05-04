Download Link: https://assignmentchef.com/product/solved-csc3320-lab-3
<br>
<span class="kksr-muted">Rate this product</span>

Purpose: Learn how to set permissions for the files and directories. Practices on editing a file via the vi editor.

Note: Please follow the instructions below step by step, and then write a report by answering the questions and upload the report (named as Lab3_FirstNameLastName.pdf or Lab3_FirstNameLastName.doc) to Google Classroom, under the rubric Lab 3 Out-of-lab Assignemnt.

Please add the lab assignment NUMBER and your NAME at the top of your file sheet.

Part 1: VI Editing – Small file

Open your terminal and connect to snowball server. Change your directory to your home directory (cd ~ ), and then create a new directory named as “Lab3” (mkdir Lab3). After that, go to directory Lab3 (cd Lab3) and please download the file “Try.c” (content shown in table below) by the following command (internet access required):

cp /home/bbello1/Public/Try.c Try.cBe sure it succeeds using “ls” to see the file name “Try.c” listed.

Try the following steps by issuing some commands in your vi editor 1) Open “Try.c” with vi editor

$vi Try.c

<ol start="2">

 <li>2)  Move cursor to the beginning of “Error!”use UP DOWN LEFT RIGHT arrow to control cursor</li>

 <li>3)  Insert “xxx”.itype “xxx” (hit x three times)</li>

 <li>4)  Append a blank line after the current line.</li>

</ol>

Hit Esc to command mode o (lowercase o)

<ol start="5">

 <li>5)  Delete “xxx”.Hit Esc to command mode.Move cursor to the beginning of “xxx”, press x three times or press 3s to delete “xxx”</li>

 <li>6)  Copy the first 2 lines, move cursor to the beginning of file, and then paste it after current line:1,2y:0 p</li>

 <li>7)  Delete the first 2 lines:1,2d</li>

 <li>8)  Save it:w</li>

 <li>9)  Replace all “fptr” with “FPTR”:1,$s/fptr/FPTR/g</li>

 <li>10)  Save and exit.:wq</li>

</ol>

1

2Part 2: VI Editing – Large file

<ol>

 <li>1)  Go into your Lab3 directory.$cd ~/Lab3</li>

 <li>2)  Copy “RealEstate.csv” from instructor’s public directory to your Lab3 directoryagain.$cp /home/bbello1/Public/RealEstate.csv .</li>

</ol>

Please write the commands you will issue to complete the following tasks and answering corresponding questions step by step in your report.

<ol start="3">

 <li>3)  Use vi to open “RealEstate.csv”.</li>

 <li>4)  Move the cursor to the last line (without knowing the number of last line).</li>

 <li>5)  Display line number.</li>

 <li>6)  Search for the transaction for the estate located at “111 EAST”Which line is this string located? (Please just write down the line number)Delete this line.</li>

 <li>7)  Move the cursor to the line 50.</li>

 <li>8)  Substitute all comma “,” with colon “:” from line 50 to line 54.</li>

 <li>9)  Copy line 50 to line 54 to the end of file.</li>

 <li>10)  Remove line 50 to line 54.</li>

 <li>11)  Describe how to enter the text mode and insert a new line “Recorded in year 2008” between line 1 and line 2.</li>

 <li>12)  Switch back to command mode.</li>

 <li>13)  Save the file and quit vi.</li>

</ol>

Part 3: Permissions for files

Follow the instructions step by step and finish the questions as required.

1) Go into your Lab3 directory.

$cd ~/Lab3

2) Check the file permissions for file “Try.c” in your own Lab3 directory.

$ls -l Try.c

3) You may see similar output as below, in which rw-rw-r– of the first field is the file permission string for “Try.c”.

[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a2c0c0c7cececd93e2c5d1d7c3c68cc5d1d78cc7c6d7">[email protected]</a>@snowball Lab3]$ ls -l Try.c-rw-rw-r–. 1 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="86e4e4e3eaeae9b7c6e1f5f3e7e2a8e1f5f3a8e3e2f3">[email protected]</a> <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="bfdddddad3d3d08effd8cccadedb91d8ccca91dadbca">[email protected]</a> 379 Sep 8 10:44 Try.c

 The leftmost 3 characters rw- tells us that the user (owner of the file) can only read and write the file.

 The middle 3 characters rw- tells us the other users in the same group as the owner can only read and write the file.

 The last 3 characters r– tells us the other users in the other groups different from owner can only read the file.

Note: once you copy a file from other directory or download a file from other resources, you are the owner of the new copied or downloaded file.

4) Remove the read permission for the owner (yourself).

$chmod u-r Try.c

5) Check the file permissions for file “Try.c” again.

$ ls -l Try.c

6) You may see similar output as below, in which -w-rw-r– of the first field is the file permission string for “Try.c”.

[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="bfdddddad3d3d08effd8cccadedb91d8ccca91dadbca">[email protected]</a>@snowball Lab3]$ ls -l Try.c–w-rw-r–. 1 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="711313141d1d1e403116020410155f1602045f141504">[email protected]</a> <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="781a1a1d14141749381f0b0d191c561f0b0d561d1c0d">[email protected]</a> 379 Sep 8 10:49 Try.c

3

So -w- in the leftmost 3 characters tells us that the user (owner of the file ) only has the permission to write something into the file.

<ol start="7">

 <li>7)  Try the vi editor again to modify the file.$vi Try.c4</li>

 <li>8)  However, you may find following message displayed at the bottom of thescreen which means you do not have the right to read “Try.c”.</li>

 <li>9)  Quit vi editor.:q</li>

</ol>

10) Try read “Try.c” again using cat.

$cat Try.c

Attach a screenshot of the output.

11) Use chmod with an octal number to let all the users only have read permission for “Try.c”.

$chmod 444 Try.c

Note: The permission string to be set should be r–r–r–. Convert each group of three characters into decimal to form an octal number, which should be 444.

12) Check the file permissions for file “Try.c” again. And explain the meaning of each character in the file permission string.

13) Try the vi editor again to modify the file. Then remove one line by pressing dd

$vi Try.cMove your cursor to some line and press dd

14) Try to save the file in the vi editor.

:w

15) Can you find some error message at the bottom of the screen? If yes, what is it and how to quit the vi editor without saving the modification.

Write answer in your answer sheet.

16) Use chmod to add write the permission to all the users for “Try.c”.

Write answer in your answer sheet.

17) Check the file permissions for file “Try.c” again. And explain the meaning of each character in the file permission string.

Write answer in your answer sheet.

Part 4: Permissions for directories

The permissions also work for the directories. However, the permissions for the directories may have different behaviors.Let us learn the permissions for directories by only changing different permissions to the owner of the file.

1) Go to your home directory and then check the permissions for directory Lab3.

$cd ~

$ls -ld ~/Lab3

Note: -d option will let you check the detailed information for the directory instead of its contents.

2) You may see similar output as below, in which rwxrwxr-x of the first field is the permission string for directory Lab3.

ls -ld ~/Lab3drwxrwxr-x. 4 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="fc9e9e99909093cdbc9b8f899d98d29b8f89d2999889">[email protected]</a> <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5537373039393a641532262034317b3226207b303120">[email protected]</a> 4096 Sep 8 11:11 /home/bbello1/Lab3

3) Use chmod with octal number to forbid all permissions to all users.

5

$chmod 000 ~/Lab3

<ol start="4">

 <li>4)  Check the permissions for directory Lab3. You may see similar output as below. The permission string is changed to ———.ls -ld ~/Lab3d———. 4 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="2f4d4d4a4343401e6f485c5a4e4b01485c5a014a4b5a">[email protected]</a> <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="9ffdfdfaf3f3f0aedff8eceafefbb1f8eceab1fafbea">[email protected]</a> 4096 Sep 11:12 /home/bbello1/Lab3</li>

 <li>5)  Finishing the following tasks and fill out the blanks in the row for owner’s permission “—” in the table below. If the task or command can be executed successfully, mark Y in the table, otherwise, mark N in the table. Please mark N/A if the task or command is not executed.</li>

</ol>

<ol>

 <li>Check the contents in directory Lab3.$ls ~/Lab3</li>

 <li>Create a directory named as “test” in Lab3.$mkdir ~/Lab3/test</li>

 <li>Create a file named as “test.txt” in Lab3.$cat&gt;~/Lab3/test.txt A test^D</li>

 <li>If (B) succeeds, remove the created directory “test” of Lab3.$rm -r ~/Lab3/test</li>

 <li>If (C) succeeds, copy “test.txt” from your Lab3 into your home directory.$cp ~/Lab3/test.txt .</li>

 <li>Go into directory Lab3.$cd ~/Lab3</li>

</ol>

6

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

The blanks in row “—” have been filled out in the table. Please compare it to your answers.

6) Fill out the blanks in other rows by repeating 3) to 5) when the owner is assigned different permissions as in the first column of the table. However, when setting the permissions, we still need to forbid all the permissions to all other users. So the last two bits in the octal number should always be kept as 00.

For example, since owner’s permissions is –x at next row, we should first set the file permission by issuing the command chmod 100 ~/Lab3. And then fill out the blanks in the row for

permissions –x by repeating 5).

Owner’s

ls

mkdir

cat &gt;

rm

cp

cd

permissions

A. Read

B. Create

C. Create file

D. Remove

E. Copy

F. Enter into

contents

sub-directory

contents

contents from

directory

—

N

N

N

N/A

N/A

N

–x

-w-

-wx

r–

r-x

rw-

rwx

Note: Since you need to try at least 56 commands, to save the time, you can press upper arrow or down arrow to repeat previous or next command.

7

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

Appendix:Table: The mapping of permissions of three characters to octal/decimal

Permissions

Binary

Octal/Decimal

—

000

0

–x

001

1

-w-

010

2

-wx

011

3

r–

100

4

r-x

101

5

rw-

110

6

rwx

111

7