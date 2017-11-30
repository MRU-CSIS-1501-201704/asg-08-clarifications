# Assignment 08 Clarifications

## List of clarifications

### Added 2017-11-30

* Opening up the current data1.txt file on a Windows machine will typically default to using the Notepad application...which will show everything on one line. (This is because of the line endings used in this file.) To get a more reasonalbe view of the data, please open it in Wordpad (which is included in Windows) or similar app.
* The houses in the data file will always be in order, with the first and last houses in the data file corresponding to the first and last houses on that block. If an attempt to insert an infill before the first house or after the last house is made, it should fail. If the first or last house is demolished, then the neighbouring houses become the first/last house on the block.
* Although it could happen in "real life", your application will not need to handle the situation where "half" of an infill is knocked down. (So for example, if we build an infill 204/206, then try to knock down 204 or 206...well, we're gonna have some troubles!) We will only be running tests where a non-infill is being demolished.
* To get full marks, you will have to create and use your own House class - it does **not** have to have the same public interface as the one provided to you - as long as the public interface you design lets the RadonProcessor do its work properly, life is good.

### Added 2017-11-29

* When saving back to file, ensure that the radon readings are saved to 5 decimal places. (Recall that a PrintWriter object responds to the same methods as System.out does, so this is an eeeeeeasy task!)
* The **only** validation that needs to be done is whether the user enters in a 1,2,3,4,5,or 6 at the main menu.

### Added 2017-11-28

* When you demolish a house, you are to reprint the houses in the block as a way of illustrating to the user that the demolition has been done properly. You should do the same thing when creating an infill.

### Added 2017-11-27

* For each public method in RadonProcessor, you need a Javadoc comment. The comment only needs a one-sentence summary of **what** (not **how**) the method does, and any @param and @return tags required for that method.
* The application should only exit when the user signals that they want to quit through the menu.
* All the houses are assumed to be on the street called "Rue Marie Curie". When you load house info from data file, make sure the houses loaded are on that street.
* You are told that in the `RadonProcessor` class, there should be a way to "print the details for **each** house". This should instead read "print the details for **a** house". This method will need to have a house number to find as a parameter.
