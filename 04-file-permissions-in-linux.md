# File Permissions in Linux

## Project description

As a security professional supporting a research team, my main goal for this project was to review the existing permissions in the team's `projects` directory and check whether each user had the right level of access. Where they didn't, I used Linux commands to update the permissions, giving the right users access and removing any access that wasn't authorized. Regularly reviewing and updating these permissions will ultimately help keep the system more secure.

## Check file and directory details

I used the `ls` command with the bundled `-la` options to list all files and subdirectories in the `projects` directory, including hidden ones, along with details like the permissions, user, group, and size of each entry.

The `ls` command lists the files and subdirectories in a directory. The `l` in `-la` tells `ls` to display the additional details of each entry, and the `a` tells it to show hidden files and subdirectories as well.

Output from `ls -la`:

```
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 20:47 .
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 21:42 ..
-rw--w---- 1 researcher2 research_team   46 Aug 21 20:47 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Aug 21 20:47 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Aug 21 20:47 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 21 20:47 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_t.txt
```

## Describe the permissions string

The permissions for the `drafts` directory are `drwx--x---`. The `d` in position 1 indicates that this entry is a directory, and it would be `-` if it were a regular file. The `rwx` in positions 2-4 indicates that the user (the owner of the file) has read, write, and execute permissions. The `--x` in positions 5-7 indicates that the group (the group that owns the file, here `research_team`) only has execute permissions. The `---` in positions 8-10 indicates that others do not have any permissions (they can't read, write, or enter the directory).

Read permissions (indicated by an `r`) for a directory allow listing the entries in that directory (read permissions for a file allow viewing the content of that file). Write permissions (indicated by a `w`) for a directory allow adding, deleting, or renaming entries in that directory (write permissions for a file allow modifying the content of that file). Execute permissions (indicated by an `x`) for a directory allow entering and traversing that directory (execute permissions for a file allow running it as a program). A `-` in place of any of those letters indicates that the permission is not granted.

## Change file permissions

Under the organization's policy, "other" users should never be able to write to a file. Based on the current permissions, `project_k.txt` was the only file that broke this rule, so I used the `chmod` command to remove write permissions for others on `project_k.txt`.

```
chmod o-w project_k.txt
```

Output from `ls -la`:

```
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 20:47 .
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 21:42 ..
-rw--w---- 1 researcher2 research_team   46 Aug 21 20:47 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Aug 21 20:47 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 21 20:47 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_t.txt
```

## Change file permissions on a hidden file

The `.project_x.txt` file is hidden because the research team archived it. Since it's archived, no one should be able to edit it, but both the user and the group still need to be able to read it. I used the `chmod` command to remove write permissions for the user and the group, and to add read permissions for the group, on `.project_x.txt`.

```
chmod u-w,g-w,g+r .project_x.txt
```

Output from `ls -la`:

```
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 20:47 .
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 21:42 ..
-r--r----- 1 researcher2 research_team   46 Aug 21 20:47 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Aug 21 20:47 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 21 20:47 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_t.txt
```

## Change directory permissions

Everything in the `projects` directory is owned by the `researcher2` user, so the `drafts` directory and its contents should only be accessible to `researcher2`. I used the `chmod` command to remove execute permissions for the group on the `drafts` directory.

```
chmod g-x drafts
```

Output from `ls -la`:

```
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 20:47 .
drwxr-xr-x 3 researcher2 research_team 4096 Aug 21 21:42 ..
-r--r----- 1 researcher2 research_team   46 Aug 21 20:47 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Aug 21 20:47 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 21 20:47 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 21 20:47 project_t.txt
```

## Summary

After reviewing the permissions of the entries in the `projects` directory using `ls -la`, I used the `chmod` command to adjust several permissions. On `project_k.txt`, I removed write permissions for others. On `.project_x.txt`, I removed write permissions for the user and the group and added read permissions for the group. On the `drafts` directory, I removed execute permissions for the group. These changes ensure that everyone, on or off the research team, only has the access they're authorized to have to each entry in the `projects` directory.
