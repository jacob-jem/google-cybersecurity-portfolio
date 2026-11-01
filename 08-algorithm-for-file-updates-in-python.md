# Algorithm for File Updates in Python

## Project description

In this project, I was tasked with developing a Python algorithm that removes IP addresses from an allow list once they no longer have access to restricted content. To accomplish this task, I first opened the allow list file in read mode and read its contents into a string variable. I then converted the string into a list and checked it against a separate list of IP addresses to remove. Once I removed the necessary IP addresses from the allow list, I converted it back into a string and wrote the new string into the allow list file, replacing the file's previous contents.

## Open the file that contains the allow list

I assigned the string `"allow_list.txt"` (the name of the allow list file) to the variable `import_file` using `=`. Then I used the `with` statement and the `open()` function to open `import_file` in `"r"` read mode (by inputting `import_file` and `"r"` as its two arguments) and used the `as` keyword to assign the resulting file object to `file`. The `with` statement automatically closes the file when the `with` block ends.

```python
# Assign `import_file` to the name of the file

import_file = "allow_list.txt"

# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# First line of `with` statement

with open(import_file, "r") as file:
```

## Read the file contents

I applied the `.read()` method to `file` and assigned the resulting string to `ip_addresses` using `=`.

```python
  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

  ip_addresses = file.read()
```

## Convert the string into a list

I used the `.split()` method on `ip_addresses` to split the one long string into a list of items based on any whitespace in the string (the default behaviour when no argument is given) and assigned the resulting list back to the `ip_addresses` variable.

```python
# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()
```

## Iterate through the remove list

I used a `for` loop, with the loop variable `element` and the `in` keyword, to iterate through `remove_list` (a list of IP addresses to remove that was provided for this task). I looped through `remove_list` because removing items from the allow list while looping over it can skip elements, and looping through `remove_list` avoids that complication.

```python
# Build iterative statement
# Name loop variable `element`
# Loop through `remove_list`

for element in remove_list:
```

## Remove IP addresses that are on the remove list

For each element in `remove_list`, I wrote an `if` conditional statement and used the `in` keyword to check whether that element was part of `ip_addresses`. If it was, I used the `.remove()` method (with that element as the argument) to remove it from `ip_addresses`. Using `.remove()` works here because the `ip_addresses` list does not contain any duplicates. Otherwise, it would only remove the first matching instance. The `if` check is also there because `.remove()` raises a `ValueError` if the item isn't in the list, so the conditional prevents a crash when an IP address on the remove list isn't on the allow list.

```python
  # Build conditional statement
  # If current element is in `ip_addresses`,

    if element in ip_addresses:

        # then current element should be removed from `ip_addresses`

        ip_addresses.remove(element)
```

## Update the file with the revised list of IP addresses

I converted the `ip_addresses` list back into a string by calling the `.join()` method on a newline character (`"\n"`) with `ip_addresses` as the argument, so that the items in the list are joined back together as one string, with each item on its own line. I then used another `with` statement and the `open()` function to open `import_file` in `"w"` write mode (by inputting `import_file` and `"w"` as its two arguments) and assigned the resulting file object to `file`. Lastly, I called the `.write()` method on `file` (with `ip_addresses` as the argument) to write the updated IP addresses into the allow list file, replacing its previous contents.

```python
# Convert `ip_addresses` back to a string so that it can be written into the text file

ip_addresses = "\n".join(ip_addresses)

# Build `with` statement to rewrite the original file

with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`

  file.write(ip_addresses)
```

## Summary

The algorithm I created first opened the allow list file using a `with` statement and the `open()` function in `"r"` read mode, then used the `.read()` method to save its contents as a string. It then used the `.split()` method to convert the string into a list. Next, it used a `for` loop with an `if` conditional nested inside it to take each IP address on the remove list, check for it in the allow list, and remove it from the allow list if it was there. Once the correct IP addresses were removed, it called the `.join()` method to convert the updated list back into a string. Lastly, it reopened the file using another `with` statement and the `open()` function in `"w"` write mode, then used the `.write()` method to write the updated IP addresses back into the file, replacing its previous contents.
