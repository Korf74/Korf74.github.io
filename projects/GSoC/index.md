---
layout: page
title: GSoC
---

# Google Summer of Code 2017 report

## Presentation of the project and work to do

[Scala Native](https://github.com/scala-native/scala-native) is an ahead of time compiler for Scala, a high-level functional language. Since Scala is built on top of Java, one goal of Scala-Native is to port some java parts in Scala-Native to make it a real scala compiler.

My work was to implement java concurrency in Scala Native, which means implementing most of **java.util.concurrent** and **java.lang.Thread**.

To do so, I had the help of the Harmony project, which implements most of its content in Java without licensing issues. Thus my work mostly consisted in porting Harmony's code in Scala, and adapt it when necessary.

## Work done

The first thing to note is that, since Scala Native is still a relatively young project, its compiler doesn't fully support all core functionalities from Javac/Scalac e.g. I didn't have access to the **synchronized** method, which shall be implemented in the future at the compiler level. Same remark for the **transient** keyword.

Most of this work was done early but wasn't runnable since a lot of java concurrency is interdependant (Threads depend on atomics for example). Some initial pull requests were closed to re-open them in a new branch **topic/multithreading**, in which multithreading tests will be done.

I began with my two first pull requests : [posix threads bindings for scala native](https://github.com/scala-native/scala-native/pull/918) and [low level atomics](https://github.com/scala-native/scala-native/pull/919) which were not ported. Atomics were implemented on top of C++ [std atomics](http://en.cppreference.com/w/cpp/atomic/atomic) with a wrapper class for each basic primitive and for references. This second PR is important since it permits two things : First, to use higher level atomics later and second, to use volatile primitives without the volatile keyword, thanks to std atomics' memory order of load and stores

Then I implemented most of **java.util.concurrent.atomic** on top of my low-level atomics, as can be seen in [this pull request](https://github.com/scala-native/scala-native/pull/930). It was quite simple since I mostly needed to forward method calling to low-level atomics.

I ported from Harmony, and with the help of my previous work **java.util.concurrent.lock.**, as can be seen in [this pull request](https://github.com/scala-native/scala-native/pull/944).

Thanks to my previous work, I was now able to implement **java.lang.{Thread, ThreadLocal, ThreadGroup}**, ported from Harmony. Java Threads are implemented on top of posix threads which means it needed some more work. I opened the pull request [here](https://github.com/scala-native/scala-native/pull/947). 
I had several issues working on Threads, such as how to correctly use pthreads as underlying java Threads, since some methods like **suspend, resume** for example don't exist in C. Suspend and resume were handled thanks to a workaround with OS signals. It is important to note that Thread cannot be used yet since it will need support for calling scala methods in native (with **CFunctionPtr** support) for Thread's **start method**, but this will be available [soon](https://github.com/scala-native/scala-native/issues/897).

Lastly, we decided that it would be nice to be able to use Scala parallel collections, but they depend on java ForkJoinPool and friends since Scala Native uses Scala 2.11, and Scala implements ForkJoinPool. Therefore I needed to implement [all java.util.concurrent classes needed for it](https://github.com/scala-native/scala-native/pull/950) and [the ForkJoin classes](https://github.com/scala-native/scala-native/pull/974). Unfortunately, as of today, this last PR doesn't compile, and I cannot find the reason why yet, but once it'll work, we'll ave support for scala parallel collections.

## Work still to do

Most of this work is untested due to a lack of time at the end of GSoC, the interdependency between PRs and the impossibility to start Threads yet. 
I lost some time near the end due to some runtime errors that were quite hard to track down.

Thus I'll need to test in depth all of my code, and it shall be reviewed by people knowing much more than me regarding Java multithreading, so that we'll be able to pull out a good and bugless concurrency together.

## Conclusion and acknowledgements

During these 3 months I learned a lot, concerning compilers, C, Scala, Java, and multithreading in general. I learned as well how to participate to an open source project and how to work in it. I always wanted to be part of an open source project, and I'm proud to have had some of my work merged.

I'm very interested in compilers and I hope to gain enough knowledge in the months to come to be able to help on more low level stuff, the real compilation part.

I'd like to thank Denys Shabalin, for his help and his quick answers, despite his huge workload. I also want to thank some of Scala Native contributors that helped me a lot, Mike Samsonov, Andrzej Sołtysik (another GSoC student), Eric Richardson, Nadav Wiener and everyone that helped me on the gitter chat. Finally I'd like to thank Google for this amazing opportunity that was given to me, I don't know if I'd ever get myself into open source witout this summer of code.

## Links

*   [Scala Native on github](https://github.com/scala-native/scala-native)
*   [std atomics](http://en.cppreference.com/w/cpp/atomic/atomic)
*   [PThreads pull request](https://github.com/scala-native/scala-native/pull/918)
*   [Low level atomics pull request](https://github.com/scala-native/scala-native/pull/919)
*   [Java atomics pull request](https://github.com/scala-native/scala-native/pull/930)
*   [Java locks pull request](https://github.com/scala-native/scala-native/pull/944)
*   [Java Threads pull request](https://github.com/scala-native/scala-native/pull/947)
*   [Java concurrent pull request](https://github.com/scala-native/scala-native/pull/950)
*   [ForkJoin pull request](https://github.com/scala-native/scala-native/pull/974)
