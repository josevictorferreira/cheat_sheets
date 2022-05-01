# Clean Architecture


## Design Principles

### SOLID

  SOLID principles tell us how to organize the functions and structures of data in classes and how the classes must be interconnected. The objective of those principles is the creation of structures of software that can be:
  - Changeable;
  - Easy of undestand;
  - The base of components that can e used in multiples softwares.

#### SRP: Single Responsability Principle

  This principle can be described by the following phrase: `A module must be responsible for one, and only one actor`. A module by the simplest definition can be understand as as one source-code file. In most of the time this definition works fine.
  SRP is useful to prevent that a code changes from a specific actor doen't produce side-effects on other actor functionality.
  It's also useful for preventing merges and code conflicts when 2 or more developers are working in the same shared resource, but with different actors.
  To avoid all this problems is necessary to separate the code that supports different actors.


#### OCP: Open/Closed Principle

  Dsescribed as `An artifact of software must be opened for extension, but closed for modification`. In another words, the behaviour of a software artifact must be extensible without changes in the artifact.
