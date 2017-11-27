# Assignment 08 Clarifications

## List of clarifications

### Added 2017-11-27

* For each public method in RadonProcessor, you need a Javadoc comment. The comment only needs a one-sentence summary of **what** (not **how**) the method does, and any @param and @return tags required for that method.
* The application should only exit when the user signals that they want to quit through the menu.
* All the houses are assumed to be on the street called "Rue Marie Curie". When you load house info from data file, make sure the houses loaded are on that street.
* You are told that in the `RadonProcessor` class, there should be a way to "print the details for **each** house". This should instead read "print the details for **a** house". This method will need to have a house number to find as a parameter.