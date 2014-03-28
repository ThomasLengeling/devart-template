#Audio.

The audio for the installation is being develop using supercollider.

To achieve audio-reactive visuals were going use a library that i'm current colaborating [MIDetectorOSC](https://github.com/beangoben/MIDetectorOSC), which sends musical information to other applications via OSC messages. This is very useful to allow perfect real-time synchronization between audio and video.

Each time there is interaction with the visuals a OSC message is send to supercollider.

the information is normalized between 0 and 1
```c
		osc::Message message;
		message.addFloatArg( lmap<float>(posx, 0, width, 0.0f, 1.0f) );
		message.addFloatArg( lmap<float>(posy, 0, height, 0.0f, 1.0f) );
		message.addFloatArg( lmap<float>(getNumberActiveParticles() 0, numberOfParticles, 0.0f, 1.0f)  );
		message.setAddress("/point"+id);
		message.setRemoteEndpoint(HOST, PORTSEND);
		sender.sendMessage(message);
```

![OSC](../project_images/osc.png "osc")

The idea is for the audience to feel deeply inserted into the piece, for that the installation draws attention to lure you in and invites more people to interact together. To make this happend we need perfect syncronization between user interaction, sound and visuals.

