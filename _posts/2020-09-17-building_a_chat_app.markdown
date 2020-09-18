---
layout: post
title:      "Building a Chat app"
date:       2020-09-18 00:08:07 +0000
permalink:  building_a_chat_app
---



I build a chat app using Socket.io for real-time data transfer, React for frontend, and Node.JS with Express for the backend. The way it works is I created two components, Dashboard.js and Store.js. Dashboard is a child component. It renders local state from my Store.  Dashboard renders al the chats, users, and channels. The user also has the ablilty to move from channel to channel by clicking on a button that's attached to an event listener. I used Node.js to implement a server connection, emit events from clients, and send a broadcast using JSON. It was a lot of fun to build and not as hard as I thought. I find the more I build and solve problems the more confident I am. I used the Store to set my initial state and ReactHooks to update the state and create actions using dispatch to send messages between users, Socket.io provided the data transfers. I will write a blog in Medium with more detail so I can add pics and show code examples and provide a link to this blog. It was so much fun to create.


Candice
