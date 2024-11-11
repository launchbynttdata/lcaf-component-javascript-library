# lcaf-component-javascript-library

This repository holds the component for Javascript library modules within the Launch Common Automation Framework (LCAF). It is intended to be widely compatible with the broad array of Javascript frameworks that exist today by separating framework-specific tasks into their own Makefiles. Targets that are generalized across multiple frameworks should be placed in the Makefile under `tasks/node`.

This component contains the following:

* linkfiles - other files used by Javascript and LCAF projects
* tasks - Makefiles for performing operations on your module and running tests and pre-checks, broken down by framework. A selection of popular frameworks is provided as a starting point, but this is intended to grow and shrink as frameworks come in and out of community favor. Framework-specific targets should be prefixed with their framework name, so in `tasks/react/Makefile` finding a `react/foo` target is acceptable. If the `foo` target was generic enough to apply to more than just React, place it under `tasks/node/Makefile`.
