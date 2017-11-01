## The Plugin System

Last year, Biohub introduced a concept called the Plugin System, with which new functions can be integrated into the platform and accessed by other users easily. However, it had several deficiencies:

 + **The framework is static**, which means the list of plugins are validated and loaded before the server starts up, and cannot be mutated during runtime. This will lower the performance if plugins are frequently installed or removed.
 + **The framework is not friendly to developers**. Neither assistant tools nor documantations are provided for target developers.
 + **The framework does not consider the cooperation with frontend**. In fact, Biohub's frontend has no awareness of the plugin mechanism. The names of the plugins and the links to them are actually hard-coded into its navigation bar.

Such flaws are fixed or improved in Biohub 2.0. The new plugin system are designed as **hot-reloadable**, as you can read in our demostration page, which allows plugin list mutations during runtime. A command-line tool `biohub-cli.py` and brief guidance as well as multiple utilities are provided to simplify the developing workflow. Based on MVVM framework Vue.js, we develop a customized mechanism to load plugins dynamically.

## ABACUS

ABACUS is one of the plugins integrated in Biohub to design amino acid sequence from a given protein. The algorithm requires an extremely large database (about 10 GiB), and will consume lots of computation resources during executing. The characteristics increase the risk of breaking down the whole server, and make the software unfriendly to those who want to test it locally.

In consideration of the issues mentioned above, we redesigned the execution model of ABACUS. Now ABACUS can be executed either locally or remotely. If the database and the binary files are configured correctly, ABACUS will be executed locally, otherwise it will forward the request to other servers who have the ability to run ABACUS locally.

Such mechanism perfectly solves the problems. On the one hand, ABACUS need not to be run in parallel with the master process of server, so the risk of breaking down doesn't exist any more. On the other hand, ABACUS can be executed without databases and binary files downloaded, .....
