`## What is Biohub 2.0?

Biohub 2.0 is a synthetic biology community, focusing on more efficient Biobricks information retrieval and more convenient biological ideas sharing. It is constructed on the basis of iGEM's official database. The parts inside are filtered and ordered intelligently, and presented to users in a friendly way. Users can grade the parts they've used, or post critical articles under them and exchange ideas with other users. All the data collected in the community will be used for more accurate ordering.

More than a community, Biohub 2.0 is also a flexible plugin system, which allows users to develop new functions and integrated them into the platform. Plugins will have full access to the community's data, so plugin developers can make further analysis of the parts. It's also welcome to deploy plugins that implement useful synthetic biological algorithms. With this mechanism, new tools and algorithms can be acquainted by other scientists more quickly.


## Motivation

The numerous parts provided by iGEM Parts Registry are precious to the biologists, but unfortunately displayed in a terrible way. For synthetic biologists with little or no knowledge about programming, the only approach to access the parts is by submitting the search box on the official pages, which is however too crude to use. The default matching algorithm defies multi-dimensional searching, and the default ordering is just wasting users' time. It's hopeless to get anything useful via this tool. Thus, a software to mine high-quality parts accurately is urgently needed.

With the data dumped from iGEM Parts Registry, which contains information like sample status or used times, the parts can be roughly ranked. But further ranking can only be accomplished after experiments are done, which requires the assistance from the whole community. Such feedback mechanism does exist in iGEM Parts Registry, which is cajlled Experiences, but is seldom used probably because of its hard-to-use interface. We think a user-friendly forum centred on Biobricks is necessary, where users can grade the parts they've used, or share experiences with other scholars. The forum on the one hand complements the data used for more accurate ranking, and on the other hand provides a platform for idea exchanging.

The parts data can be used for various purposes, but apparently we are not able to achieve all of them. In consideration of this, we decide to make our software extensible. Developers with ideas to better make use of the data may develop their own plugins, and embed them into the software. With the help of forum, such plugins will be acquainted quickly, and accelerate the development of synthetic biology.

## Implementation

### Server Part
The server of Biohub 2.0 is written in Python 3.6 and we choose Django as our basic framework. We added many features to the framework to enable our plugin system, like hot reloading and websocket routing. The underlying implementation of Django had been carefully patched to meet our need for changeable core components.

### Frontend Part
Biohub 2.0 is a single page application using Bootstrap and Vue.js as its frameworks. We do not design our user interface with the existing components in Bootstrap but the customed one. Several libraries, like ngl.js and d3.js, were used to visualize the data. 
<!-- to do -->

## To Be Improved

As an upgrade version of Biohub 1.0, we've achieved quite a lot, but there's still something imperfect, due to technical or time limitation. One is that users cannot upload their own plugins freely as a consideration of security. We will try to add sand-box mechanism in the future, whilst still providing enough freedom for plugins. Another is that the project lacks a scaffold for plugin developers, which may confuse them while setting up developing environment. Also, the plugin system lacks a detailed documantation for developers. We will keep updating the repository and gradually fill these blanks in the future.
`