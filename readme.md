# Project Name
ProjectPhoenix

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
    - [Compiling and Running ](#compiling-and-running )



## Introduction
This repo contains source code for telemetry of projectPhoenix

## Prerequisites
Ubuntu 22.02 or Debian 12  (https://www.debian.org/distrib/) (https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)
Clion 2023.3.2 or newer (https://www.jetbrains.com/fr-fr/clion/download/#section=linux)   
Cmake 3.27 or newer   

## Getting Started

1. Open the project with CLion 
2. To install needed apt packages, run the script scripts/InstallPackages.sh 
3. If Cmake project is not detected, right click on CmakeLists.txt at the root of the project and click load CMake Project
4. Click On File | Settings | Build, Execution, Deployment | Cmake and enable release_build and debug_build , disable the other ones

### Compiling and Running 
1. Select OCD ProjectPhoenix as the run config
2. To run in debug mode, select the config debug_build and click the debug button (stm32 must be connected via USB)
3. To run in release mode, select the config release_build and click the debug button (stm32 must be connected via USB)
