# EarthWalkSoftware/kaptain-menu-debian

### kaptain-menu-debian

*kaptain-menu-debian* is a docker image, layered on top of *EarthWalkSoftware/kaptain-debian*, which provides a framework for implementing menu templates for use with *Kaptain*.  The framework facilitates loading, modification, and storage of menu templates, and the generation of the command line for direct execution and/or storage as a bash command script.

_____________________

### Kaptain

*Kaptain* is a universal graphical front-end tool for creating dialog-based interfaces for command-line programs, and an *API* for creating a graphical user interface for a command-line program without having to learn a programming language or how to embed a graphical library in an application.

*EarthWalkSoftware/kaptain-debian* is an implementation of *Kaptain* in a docker image.  For more information refer to

  https://github.com/EarthWalkSoftware/kaptain-menu-debian

________

### Using kaptain-menu-debian


    docker run -v ${HOME}/bin:/userbin \
               -v ${HOME}/.config/docker:/menu \
               -v /etc/localtime:/etc/localtime:ro \
               -v /tmp/.X11-unix:/tmp/.X11-unix \
               -v /tmp/.docker.xauth:/tmp/.docker.xauth \
               -v ${HOME}/.Xauthority:${HOME}/.Xauthority \
               -e DISPLAY=unix${DISPLAY} \
               -e KPT_USER=${USER} \
               -e KPT_UID=${UID} \
               -e KPT_HOME=${HOME} \
               -e KPT_MENU=kaptain-menu-sample \
               --name=kaptain-menu \
               --rm \
           kaptain-menu-debian:latest

