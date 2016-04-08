# streembit
P2P, decentralized, real time, secure communication system for humans and machines.

http://streembit.github.io/

What is Streembit?
-----------------

Streembit is an experimental decentralised communication system for humans and 
Internet of Things devices. The purpose of Streembit is to create a free, secure, 
decentralised, peer to peer, open source system that secures your real time communication. 
You can have as many accounts on the permissionless Streembit network as you want. 
No registration, no email address, no personal details are required. 
Streembit will not spam users with ads. Instead of using centralised corporate clouds, 
Streembit runs on a community driven, decentralised, P2P overlay network. 
Streembit uses peer-to-peer technology to operate with no central authority: 
discovering contacts, persisting the data and routing  messages are carried out collectively by the network. 

For more information and an immediately useable, binary version of the Streembit software, see http://streembit.github.io/download.

License
-------

Streembit is a completely free and open source software. Streembit is released under the terms of the GNU General Public License. See [COPYING](https://github.com/streembit/streembit/blob/master/LICENSE) for more information or see http://www.gnu.org/licenses/.


Modules
-------

Streembit is the composite of the following fully open source modules, libraries and projects:

**streembitlib**   
Streembit Kademlia, JWT, JWE and crypto Node.js libraries. https://github.com/streembit/streembitlib


**streembitseed**    
Streembit seed application is seed node on the Streembit network. https://github.com/streembit/streembitseed


**streembitui**    
Streembit user interface. Cross platform, Windows, Linux and MAC OS X desktop application. https://github.com/streembit/streembitui


Build Streembit
--------------

The Streembit Core software is a Node.js application which uses the NW.js(node-webkit) library. NW.js is an app runtime based on Chromium. In order to build Streembit from source you must be familiar with Node.js, the Chromium project and NW.js (node-webkit).

To build Streembit from source first you must build Chromium software and the NW.js (node-webkit) library. 

To build Chromium please refer to the Chromium project web site.

[Build summary](https://www.chromium.org/nativeclient/how-tos/build-tcb)
 
[Get the Chromium code](http://www.chromium.org/developers/how-tos/get-the-code)
 
[Windows build instructions](https://chromium.googlesource.com/chromium/src/+/master/docs/windows_build_instructions.md)

To build NW.js please refer to the NW.js [build documentation](http://docs.nwjs.io/en/latest/For%20Developers/Building%20NW.js/).


Run Streembit from source 
------------------------

Once Chromium and NW.js are built clone the streembit repository:  

```bash
$ git clone https://github.com/streembit/streembit
$ cd /streembit
```

Install the Streembit Node.js dependencies:  

```bash
$ npm install
```

Run Streembit:  
```bash
$ /path/to/nw . 
```
(The node-webkit executables must be in the /nw directory if you run the above command. The package.json file must exists in the Streembit directory).



Build and create the Streembit executable
-----------------------------------------

Once you have built Chromium and NW.js, create the Streembit package by running the platform specific build file from the Streembit/build source directory.

Windows 64-bit build:  
Build node-webkit from source or download the latest Windows 64-bit node-webkit binaries from the node-webkit project site, and copy it to the /build/buildtools/win64 directory.  
Execute the build/build_win64.bat file from the windows command line.

Linux 64-bit build:  
Build node-webkit from source or download the latest Linux 64-bit node-webkit binaries from the node-webkit project site, and copy it to the /build/buildtools/linux64 directory.    
Execute the build/build_linux64.sh file from the Linux terminal.

MacOS build:  
Build node-webkit from source or download the latest MAC OS X node-webkit binaries from the node-webkit project site, and copy it to the /build/buildtools/macosx directory.   
Execute the build/build_macos64.sh file from the terminal.



Build the streembitseed application
-----------------------------------

To help and contribute to the stability of Streembit network please run the streemo-seed application. More seeds make the network more stable and having more seeds deployed we can mitigate DDoS attacks and government interventions more effectively.  Also, if you wish to run your own Streembit network you must run your own streembitseed nodes. streembitseed is a Node.js application based on the streembitlib library, but without the Chromium/NW.js UI components. To build streembit-seed from source clone the [streembitseed source](https://github.com/streembit/streembitseed.git) and follow the instructions of to the readme.



Contributing to Streembit
-------------------------

The Streembit project operates an open contributor model where anyone is welcome to contribute towards development in the form of peer review, testing and patches. This document explains the practical process and guidelines for contributing.

Firstly in terms of structure, there is no particular concept of “Core developers” in the sense of privileged people. Open source often naturally revolves around meritocracy where longer term contributors gain more trust from the developer community. However, some hierarchy is necessary for practical purposes. As such there are repository “maintainers” who are responsible for merging pull requests as well as a “lead maintainer” who is responsible for the release cycle, overall merging, moderation and appointment of maintainers.


Contributor Workflow
--------------------

The codebase is maintained using the “contributor workflow” where everyone without exception contributes patch proposals using “pull requests”. This facilitates social contribution, easy testing and peer review.

To contribute a patch, the workflow is as follows:

  - Fork repository
  - Create topic branch
  - Commit patches

The project coding conventions in [doc/developer-notes.md](doc/developer-notes.md) must be adhered to.

In general [commits should be atomic](https://en.wikipedia.org/wiki/Atomic_commit#Atomic_commit_convention) and diffs should be easy to read. For this reason do not mix any formatting fixes or code moves with actual code changes.

Commit messages should be verbose by default consisting of a short subject line (50 chars max), a blank line and detailed explanatory text as separate paragraph(s); unless the title alone is self-explanatory (like "Corrected typo in main.js") then a single title line is sufficient. Commit messages should be helpful to people reading your code in the future, so explain the reasoning for your decisions. Further explanation [here](http://chris.beams.io/posts/git-commit/).

If a particular commit references another issue, please add the reference, for example "refs #1234", or "fixes #4321". Using "fixes or closes" keywords will cause the corresponding issue to be closed when the pull request is merged.

Please refer to the [Git manual](https://git-scm.com/doc) for more information about Git.

  - Push changes to your fork
  - Create pull request

The title of the pull request should be prefixed by the component or area that the pull request affects. Examples:

    Consensus: Add new UI for ATMEL Xplained board
    Net: Pull contact messages from multiple seeds
    UI: Add record video button
    Trivial: fix typo

If a pull request is specifically not to be considered for merging (yet) please prefix the title with [WIP] or use [Tasks Lists](https://github.com/blog/1375-task-lists-in-gfm-issues-pulls-comments) in the body of the pull request to indicate tasks are pending.

The body of the pull request should contain enough description about what the patch does together with any justification/reasoning. You should include references to any discussions (for example other tickets or mailing list discussions).

At this stage one should expect comments and review from other contributors. You can add more commits to your pull request by committing them locally and pushing to your fork until you have satisfied all feedback. If your pull request is accepted for merging, you may be asked by a maintainer to squash and or rebase your commits before it will be merged. The length of time required for peer review is unpredictable and will vary from patch to patch.


Pull Request Philosophy
-----------------------

Patchsets should always be focused. For example, a pull request could add a feature, fix a bug, or refactor code; but not a mixture. Please also avoid super pull requests which attempt to do too much, are overly large, or overly complex as this makes review difficult.


###Features

When adding a new feature, thought must be given to the long term technical debt and maintenance that feature may require after inclusion. Before proposing a new feature that will require maintenance, please consider if you are willing to maintain it (including bug fixing). If features get orphaned with no maintainer in the future, they may be removed by the Repository Maintainer.


###Refactoring

Refactoring is a necessary part of any software project's evolution. The following guidelines cover refactoring pull requests for the project.

There are three categories of refactoring, code only moves, code style fixes, code refactoring. In general refactoring pull requests should not mix these three kinds of activity in order to make refactoring pull requests easy to review and uncontroversial. In all cases, refactoring PRs must not change the behaviour of code within the pull request (bugs must be preserved as is).

Project maintainers aim for a quick turnaround on refactoring pull requests, so where possible keep them short, uncomplex and easy to verify. 


Decision Making Process
-------------------------

The following applies to code changes to the Streembit project and related projects such as streembit-seed.

Whether a pull request is merged into Streembit rests with the project merge maintainers and ultimately the project lead. 

Maintainers will take into consideration if a patch is in line with the general principles of the project; meets the minimum standards for inclusion; and will judge the general consensus of contributors.

In general, all pull requests must:

  - have a clear use case, fix a demonstrable bug or serve the greater good of the project (for example refactoring for modularisation);
  - be well peer reviewed;
  - have unit tests and functional tests where appropriate;
  - follow code style guidelines;
  - not break the existing test suite;
  - where bugs are fixed, where possible, there should be unit tests demonstrating the bug and also proving the fix. This helps prevent regression.

Patches that change Streembit consensus rules are considerably more involved than normal because they affect the entire ecosystem and so must be preceded by extensive mailing list discussions and have a numbered BIP. While each case will be different, one should be prepared to expend more time and effort than for other kinds of patches because of increased peer review and consensus building requirements.


###Peer Review

Anyone may participate in peer review which is expressed by comments in the pull request. Typically reviewers will review the code for obvious errors, as well as test out the patch set and opine on the technical merits of the patch. Project maintainers take into account the peer review when determining if there is consensus to merge a pull request (remember that discussions may have been spread out over github, mailing list and IRC discussions). The following language is used within pull-request comments:

  - ACK means "I have tested the code and I agree it should be merged";
  - NACK means "I disagree this should be merged", and must be accompanied by sound technical justification. NACKs without accompanying reasoning may be disregarded;
  - utACK means "I have not tested the code, but I have reviewed it and it looks OK, I agree it can be merged";
  - Concept ACK means "I agree in the general principle of this pull request";
  - Nit refers to trivial, often non-blocking issues.

Reviewers should include the commit hash which they reviewed in their comments.

Project maintainers reserve the right to weigh the opinions of peer reviewers using common sense judgement and also may weight based on meritocracy: Those that have demonstrated a deeper commitment and understanding towards the project (over time) or have clear domain expertise may naturally have more weight, as one would expect in all walks of life.

Where a patch set affects consensus critical code, the bar will be set much higher in terms of discussion and peer review requirements, keeping in mind that mistakes could be very costly to the wider community. This includes refactoring of consensus critical code.


Release Policy
--------------

The project leader is the release manager for each Streembit release.

