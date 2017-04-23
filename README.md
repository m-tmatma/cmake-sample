# cmake-sample

This repository shows how to use cmake

## HelloWorld

This is a HelloWorld project for cmake

## LibrarySample

This is a project which uses a static or shared library

usage:

if you want use static libary, you run cmake with -D BUILD_SHARED_LIBS=0

<pre><code>
cmake -D BUILD_SHARED_LIBS=0 ..\cmake-sample\LibrarySample\
</code></pre>

if you want use shared libary, you run cmake with -D BUILD_SHARED_LIBS=1

<pre><code>
cmake -D BUILD_SHARED_LIBS=1 ..\cmake-sample\LibrarySample\
</code></pre>

