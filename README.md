# Assignment 08 Clarifications

## List of clarifications

### Added 2017-12-03

* You can assume that if an infill is built in the middle of the block, the tests will only do so if there are houses on either side of the infill. (This makes calculating the infill's basements' radon levels less of a pain.)

### Added 2017-12-02

* Houses (and "empty lots" available for infills) will only be on the **odd** side of the street; the first house (or first available location for building an infill) will always be blahblah**01**. (For example 1501, 101, 3701, etc.)
    * **clarification of this clarification** Though we will not try to build a house **before** xxx01, your code should be able to handle situations where an infill built **after** xxx01 might become the first house! (For example, say 1509 is currently the first house. Then if an infill is put up at 1505/1507, then it will become the first house...and you have to make sure you handle calculation of the avg daily Radon readings in that infill correctly!) 
* When demolishing a house, the **only** error checking you need to do is to see whether a house with that number exists or not. (i.e. whether a house with the given number exists in the ArrayList.)


### Added 2017-11-30

* Opening up the current data1.txt file on a Windows machine will typically default to using the Notepad application...which will show everything on one line. (This is because of the line endings used in this file.) To get a more reasonalbe view of the data, please open it in Wordpad (which is included in Windows) or similar app.
* The houses in the data file will always be in order, with the first and last houses in the data file corresponding to the first and last houses on that block. <del>If an attempt to insert an infill before the first house or after the last house is made, it should fail.</del> If the first or last house is demolished, then the neighbouring houses become the first/last house on the block.
  * **correction**: Infills **can** be built before the current first house or after the current last house on the block.
* Although it could happen in "real life", your application will not need to handle the situation where "half" of an infill is knocked down. (So for example, if we build an infill 204/206, then try to knock down 204 or 206...well, we're gonna have some troubles!) We will only be running tests where a non-infill is being demolished.
* To get full marks, you will have to create and use your own House class - it does **not** have to have the same public interface as the one provided to you - as long as the public interface you design lets the RadonProcessor do its work properly, life is good.

### Added 2017-11-29

* When saving back to file, ensure that the radon readings are saved to 5 decimal places. (Recall that a PrintWriter object responds to the same methods as System.out does, so this is an eeeeeeasy task!)
* The **only** validation that needs to be done is whether the user enters in a 1,2,3,4,5,or 6 at the main menu.

### Added 2017-11-28

* <del>When you demolish a house, you are to reprint the houses in the block as a way of illustrating to the user that the demolition has been done properly. You should do the same thing when creating an infill.</del>
 * **correction 2017-12-02** We have decided to have the automated tests do the reprinting instead (by selecting menu option 1). Your demolition and infill code should only print out a success or failure message.

### Added 2017-11-27

* For each public method in RadonProcessor, you need a Javadoc comment. The comment only needs a one-sentence summary of **what** (not **how**) the method does, and any @param and @return tags required for that method.
* The application should only exit when the user signals that they want to quit through the menu.
* All the houses are assumed to be on the street called "Rue Marie Curie". When you load house info from data file, make sure the houses loaded are on that street.
* You are told that in the `RadonProcessor` class, there should be a way to "print the details for **each** house". This should instead read "print the details for **a** house". This method will need to have a house number to find as a parameter.


## Hints for error messages

In order for your code to pass the automated tests, the following must be true of your program's error messages:

* If the user enters in an invalid menu option (like "foo" or "8"), your error message should contain the phrase **illegal choice**.
    * Ex. "That was an illegal choice. Please enter a number between 1 and 6."
* (Menu Option 2, 3) If the user enters in a house number, but no such house exists, your error message should contain the phrase **no house**.
    * Ex. "No house with that number exists."
* (Menu Option 4) If the user enters in a number for an infill, but that number isn't a possible house number on the street, then your error message should contain the phrase **not a valid house number for this block**.
    * Ex. "Can't build an infill there - it is not a valid house number for this block."
* (Menu Option 4) If the user enters in a number for an infill, but a house already exists there, your error message should contain the phrase **not vacant**.
    * Ex. "You can't put an infill there; the location is not vacant."
