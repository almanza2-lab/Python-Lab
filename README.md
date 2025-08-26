# Python Lab

[View the full project document with screenshots on Google Docs](https://docs.google.com/document/d/1T9YalcOcqbxsutCR89xmwgb1nhUWtKDG09Gd9UqySPY/edit?usp=sharing)

## Objective
This project is to create an algorithm that uses Python code to check whether ip addresses on the remove list are also on the allow list. The code should ensure that those addresses that are on the remove list are deleted from the allow list.

Since access to restricted content is based on the allow list, this will ensure that the allow list is kept up to date and will adhere to the principle of least privilege.


## Skills Learned

* **Python Programming:** Gained practical experience with Python, including file input/output operations, string manipulation, and the use of the `with` statement for efficient resource management.
* **Data Structure Manipulation:** Developed the ability to transform data by converting a string of text into a list for processing and back into a string for writing to a file.
* **Process Automation:** Acquired skills in designing and implementing an automated process to handle a repetitive task, such as updating an IP allow list, to improve efficiency and reduce human error.
* **Documentation:** Learned how to clearly document code and project logic, as demonstrated by the step-by-step breakdown of the algorithm.

### Tools Used


- Python.

## Steps


## Open the file that contains the allow list

The first step will be to open the file that contains the allow list. To do that we will use the following code:

* `with` Statement: This is a context manager that ensures the file is properly opened and closed, even if an error occurs while processing the file.
* `open(import_file, "r")`: The open() function is used to open a file.
    * `import_file` is a variable representing the file name or path.
    * `"r"` stands for "read mode," meaning the file is opened for reading only.
* `as file`: This assigns the opened file object to the variable `file`, allowing you to interact with the file within the `with` block.

## Read the file contents

Next we type the following code:

* `file.read()`: This calls the `read()` method on the file object.
    * It reads the entire content of the file as a single string.
* `ip_addresses =`: This assigns the output of `file.read()` (the file's content) to the variable `ip_addresses`.
    * `ip_addresses` will now store the entire content of the file as a string.

## Convert the string into a list

To convert the file from a string into a list we type the following code:

* `ip_addresses.split()`: This calls the `.split()` method on the string stored in `ip_addresses`.
    * By default, `.split()` divides the string wherever it encounters whitespace (spaces, tabs, or newlines).
    * It returns a list of words (or, in this case, IP addresses if they are separated by spaces or newlines).
* `ip_addresses =`: This assigns the result of `ip_addresses.split()` (a list) back to the `ip_addresses` variable.
    * The original string is replaced with a list where each element is a separate item from the original text.

## Iterate through the remove list

Next we will enter the following code to iterate through the remove list:

* `for loop`: This initiates a loop that iterates over each item in the `ip_addresses` list.
* `element`: This is a loop variable that represents the current item from `ip_addresses` during each iteration.
* `in ip_addresses`: This specifies that the loop should iterate over each item in the `ip_addresses` list.

## Remove IP addresses that are on the remove list

Next we will need to remove the IP addresses that are on the remove list. To do this we enter the following code:

* `if element in remove_list:`
    * This checks if the current `element` (from the loop) is present in `remove_list`.
    * `remove_list` is a list of IP addresses that should be removed from `ip_addresses`.
    * If `element` is found in `remove_list`, the condition evaluates to `True`, and the indented code runs.
* `ip_addresses.remove(element)`
    * If the condition is `True`, this line removes `element` from the `ip_addresses` list.
    * `.remove(element)` finds and deletes the occurrence of `element` in the list.

## Update the file with the revised list of IP addresses

Finally, we need to update the file with the revised list of IP addresses. To do this we use the following code:

* `" ".join(ip_addresses)`
    * The `.join()` method is used to convert a list (`ip_addresses`) into a single string.
    * `" "` (a space) is the separator placed between each element in the list.
* `ip_addresses =`
    * This assigns the newly created string back to the `ip_addresses` variable, replacing the list with the formatted string.
* `with open(import_file, "w") as file:`
    * Opens the file specified by `import_file` in write mode (`"w"`).
    * `"w"` means any existing content in the file will be erased, and new content will be written.
    * The `with` statement ensures the file is automatically closed after writing, preventing data loss or corruption.
* `file.write(ip_addresses)`
    * Writes the string stored in `ip_addresses` to the file.
    * Since `ip_addresses` is now a single string with IPs separated by spaces, the file will contain them in one line.

## Summary

This algorithm manages an allowlist of IP addresses by removing specific addresses from a file. It starts by defining the file name and a list of IP addresses to be removed. The file is then opened in read mode, and its contents are read and converted into a list using the `.split()` method. A loop iterates through the list, checking if each IP address is in the removal list and deleting any matches. After filtering, the modified list is converted back into a space-separated string. Finally, the file is opened in write mode, and the updated list of IP addresses is written back, replacing the original content.




