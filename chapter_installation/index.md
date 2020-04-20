# Installation
:label:`chap_installation`

In order to get you up and running for hands-on learning experience,
we need to set you up with an environment for running Python,
Jupyter notebooks, the relevant libraries,
and the code needed to run the book itself.

## Installing JDK 11 (not jre)

JDK 11 (or above are required) to run the examples provided in this folder.

to confirm the java path is configured properly:

```
java --list-modules | grep "jdk.jshell"

> jdk.jshell@12.0.1
```

## Install jupyter notebook on python3
Use the following command to install Jupyter Notebook in Python 3:
```
pip3 install jupyter
```

## Install Java kernel for jupyter notebook

By default jupyter notebook runs on Python3, you need to install Java kernel to run DJL.

```bash
git clone https://github.com/frankfliu/IJava.git
cd IJava/
./gradlew installKernel
``` 

## Downloading the D2L-Java Notebooks

Next, we need to download the code of this book. You can use the
[link](https://d2l.ai/d2l-en-0.7.1.zip) to download and unzip the code.
Alternatively, if you have `unzip` (otherwise run `sudo apt install unzip`) available:

```bash
mkdir d2l-java && cd d2l-java
curl https://d2l.ai/d2l-en.zip -o d2l-en.zip
unzip d2l-java.zip && rm d2l-java.zip
```


Now we will want to activate the `d2l` environment and install `pip`.
Enter `y` for the queries that follow this command.

```bash
conda activate d2l
conda install python=3.7 pip -y
```


## Running jupyter notebook

Once above dependencies are installed, we now open the Jupyter notebook by running:

```bash
jupyter notebook
```


At this point, you can open http://localhost:8888 (it usually opens automatically) in your Web browser. Then we can run the code for each section of the book.
Remember to switch the Kernel to Java instead of Python3.

## Adding dependencies on DJL and MXNet engine

You can add DJL dependencies and MXNet engine from maven directly:

```java
// Add the snapshot repository to get the DJL snapshot artifacts
// %mavenRepo snapshots https://oss.sonatype.org/content/repositories/snapshots/

// Add the maven dependencies
%maven ai.djl:api:0.4.0
%maven org.slf4j:slf4j-api:1.7.26
%maven org.slf4j:slf4j-simple:1.7.26
        
// See https://github.com/awslabs/djl/blob/master/mxnet/mxnet-engine/README.md
// for more MXNet library selection options
%maven ai.djl.mxnet:mxnet-native-auto:1.6.0
```

Now you can import and run different modules in DJL.


## GPU Support

TBD

## Exercises

1. Download the code for the book and install the runtime environment.


## [Discussions](https://discuss.mxnet.io/t/2315)

![](../img/qr_install.svg)
