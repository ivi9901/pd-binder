[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ivi9901/pd-binder.git/HEAD)

This is the repository of the course on Functional Programming in
Scala taught at the University Rey Juan Carlos. 

# Content 

The course basically includes several notebooks on the following topics:

* PF-1.1 Object-oriented Scala
* PF-2.1 Functions and algebraic data types
* PF-2.2 Recursive functions and ADTs
* PF-2.3 The Curry-Howard correspondence
* PF-3.1 The Hall-of-Fame of HOFs
* PF-3.2 HOFs as a query language

# Intro & Schedule

[Intro.pdf](Intro.pdf) -- (Spanish, URJC specifics)

# Launching notebooks

To access these notebooks you need first to install [git](https://git-scm.com/) and clone this repository in your local drive: 

`> git clone https://github.com/jserranohidalgo/urjc-pd.git pd`

Then, run the program:

`jupyter notebook` 

in the root directory of the repository, if you already installed
`jupyter` in your computer (see instructions below).

Alternatively, you can skip the manual installation of `jupyter`
and run it through [docker](https://hub.docker.com/editions/community/docker-ce-desktop-windows) as follows:

`docker run -it --rm -p 8888:8888 -p 4040:4040 -m 4g -v "$PWD":/home/jovyan/work almondsh/almond:latest` (LINUX)

`docker run -it --rm -p 8888:8888 -p 4040:4040 -m 4g -v <<c:/path/to/downloaded/folder>>:/home/jovyan/work almondsh/almond:latest` (WINDOWS)

(also in the root directory of the repository)

Finally, note that `jupyter` is already installed in the virtual
environment MyApps (just for URJC users).

# Installing jupyter and the Scala kernel

To install jupyter and run Scala notebooks, follow these steps:

* Install the package manager [`conda`](https://docs.conda.io/en/latest/miniconda.html), or use `pip`, the python package manager.
* Install [`jupyter`](https://jupyter.org/install) itself
* Alternatively, you can also find jupyter notebooks for free when installing [anaconda](https://www.anaconda.com/products/individual-d).
* Install the Scala plugin [`almond`](https://almond.sh/docs/quick-start-install)

### Possible problems when installing almond

* The installation command hangs (most likely, on windows)

Execute the installation command with the verbose option enabled (`-v -v`):

        .\coursier launch --fork almond -M almond.ScalaKernel -v -v -- --install

When the program hangs, stop it (C-c C-c). Most likely, the last command that was attempted was something like "Running java ...". Copy-paste that java invocation and run it manually:

        java -Dscala-kernel.version=<...> -jar <...> --install

Luckily, this will complete the installation of the almond kernel.

* "Cannot find default main class. Specify one with -M or --main-class" (most likely, on linux)

Add the option `-M almond.ScalaKernel`  to the installation command, i.e.

        ./coursier launch --fork almond -M almond.ScalaKernel -- --install


<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
