# User Guide

This product is not meant for end-users and therefore there is no user-friendly installer. 
Please refer to the [Setting up](DeveloperGuide.md#setting-up) section to learn how to set up the project.

## Starting the program

1. Find the project pane (usually located at the left side)
2. Open up `src/seedu.addressbook` folder
3. Right click on `Main`
4. Click `Run Main.main()`
5. The GUI should appear in a few seconds

<img src="images/Ui.png">

## Viewing help : `help`
Format: `help`

> Help is also shown if you enter an incorrect command e.g. `abcd`
 
## Adding a person: `add`
Adds a person to the address book<br>
Format: `add NAME [p]p/PHONE_NUMBER [p]e/EMAIL [p]a/ADDRESS [t/TAG]...` 
 
> Words in `UPPER_CASE` are the parameters, items in `SQUARE_BRACKETS` are optional, 
> items with `...` after them can have multiple instances. Order of parameters are fixed. 
> 
> Put a `p` before the phone / email / address prefixes to mark it as `private`. `private` details can only
> be seen using the `viewall` command.
> 
> Persons can have any number of tags (including 0)

Examples: 
* `add John Doe p/98765432 e/johnd@gmail.com a/John street, block 123, #01-01`
* `add Betsy Crowe pp/1234567 e/betsycrowe@gmail.com pa/Newgate Prison t/criminal t/friend`

## Listing all persons : `list`
Shows a list of all persons in the address book.<br>
Format: `list`

## Finding all persons containing any keyword in their name: `find`
Finds persons whose names contain any of the given keywords.<br>
Format: `find KEYWORD [MORE_KEYWORDS]`

> The search is case insensitive, the order of the keywords does not matter, only the name is searched,
and persons matching at least one keyword will be returned (i.e. `OR` search).

Examples: 
* `find John`<br>
  Returns `John Doe` and `john`
* `find Betsy Tim John`<br>
  Returns Any person having names `Betsy`, `Tim`, or `John`

## Deleting a person : `delete`
Deletes the specified person from the address book. Irreversible.<br>
Format: `delete INDEX`

> Deletes the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `delete 2`<br>
  Deletes the 2nd person in the address book.
* `find Betsy`<br> 
  `delete 1`<br>
  Deletes the 1st person in the results of the `find` command.

## View non-private details of a person : `view`
Displays the non-private details of the specified person.<br>
Format: `view INDEX`

> Views the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `view 2`<br>
  Views the 2nd person in the address book.
* `find Betsy` <br> 
  `view 1`<br>
  Views the 1st person in the results of the `find` command.

## View all details of a person : `viewall`
Displays all details (including private details) of the specified person.<br>
Format: `viewall INDEX`

> Views all details of the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `viewall 2`<br>
  Views all details of the 2nd person in the address book.
* `find Betsy`<br> 
  `viewall 1`<br>
  Views all details of the 1st person in the results of the `find` command.

## Clearing all entries : `clear`
Clears all entries from the address book.<br>
Format: `clear`  

## Exiting the program : `exit`
Exits the program.<br>
Format: `exit`  

## Saving the data 
Address book data are saved in the hard disk automatically after any command that changes the data.<br>
There is no need to save manually. Address book data are saved in a file called `addressbook.txt` in the project root folder.
