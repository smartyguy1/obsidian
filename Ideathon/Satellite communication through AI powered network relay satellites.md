
# What are satellites?
Satellites are essential space exploration and communication devices that orbit around a celestial body. I am going to talk about deep space and space exploration satellites. These satellites are composed of sophisticated devices whose uses range from, imaging, data-collecting, data processing and data transmitting. 
*Examples of satellites:* Mangalyaan,  

# Issues with traditional satellite communication

Traditional satellite communication methods suffer with issues such as
- High latency 
- Data loss due to transmission through large distances
- Communication black outs due to physical obstructions
- Inability to make quick decisions due to latency of data received

### Example:
##### Chandrayaan-2 Mission:

During the Chanrayaan-2 mission of 2019, the Vikram Lander lost communication with ISRO about 2.1 Km above the lunar surface. One of the causes for this communication failure was that the thrust control algorithm was configured to apply corrections towards the end of descent phase-1 and not instantaneously, allowing large navigation errors to be accumulated. Another major cause if this failure was a Software glitch of the guidance software. 

**What do I propose?**
# Relay Satellites

Satellites in orbit cannot pass along their information to the ground stations on Earth if the satellite does not have a clear view of the ground station. Therefore, TDRS(Tracking and Data Relay Satellites) serve as a path to pass along the satellite’s information. Think of it like how the baton is passed between racers during a relay race. Another example is how when we want to increase the range of our wifi network we install devices like boosters, extenders or repeaters.

The main satellite will than have access to a large network of relay satellites. Through this large network, when the main satellite wants to send some information to Earth, It's AI can use path finding algorithms such as Dijkstra's Algorithm, A* Algorithm etc. to this large network to find the shortest path through which to send the Data.

These small satellites can then form a chain, or more accurately a train of data transmission which will transmit the data from the Deep space or main satellite through multiple relay satellites to the receivers on Earth. This ensures seamless data transmission with minimal interference and also allows decisions and plans for the satellite to be implemented more quickly.


### Benefits

 - **Reduced Latency:** By using multiple relay satellites, the data can take a more direct path to Earth, bypassing the need for the exploration satellite to wait until it has a direct line of sight with Earth.
- **Continuous Communication:** A constellation of relay satellites can provide near-continuous communication coverage, even when the exploration satellite is on the far side of a planet or obstructed by other celestial bodies.
- **Efficient Data Transfer:** Multiple relay nodes can distribute the data load, reducing the chance of bottlenecks and enabling higher data transmission rates.
- **Scalability:** The network can be expanded with more satellites as needed, enhancing coverage and capacity.
### Challenges:

This fixes the problems we talked about a minute ago but raises other problems that I am going to discuss one-by-one.

- **Complexity:** Managing a network like this would be an absolute nightmare since it requires precise coordination, especially maintaining their orbits and ensuring stable inter-satellite communication links.

	- Well one solution could be for the satellites to keeping sending each other's coordinates so every satellite has information about the network. This does give precision but is going to consume more power. 
	- Another solution could be that each satellite gets the coordinates of the satellites *closest* to it and then sends these back to the main satellite which can than decide the optimal route through which to transmit the data.

- **Power and Bandwidth**: Small satellites have limited power and bandwidth compared to larger, dedicated satellites which could constrain their ability to handle large volumes of data.

	- This can be done by dividing the data into small chunks and then distributing them throughout the network and then transmitting it to Earth along with a "manual" that shows how to recombine the file. This way power consumption can be kept minimum while ensuring low latency since the small chunks of data will be transmitted faster.
	
	- Another thing we could do would be to enable the main satellite and network satellites to communicate with other dedicated satellites. For eg: Suppose we have sent a satellite to Venus for research purposes. That satellite wants to process and send a large chunk of data to us. Now, suppose that Venus at that time happens to be far from us but Mars is midway between them. The Venus satellite could then ask the *Mangalyaan* for help in processing and sending the data. Since Mangalyaan is not occupied with any major data-processing it could get half the data from the Venus satellite, process it and send it to Earth. 
 
 - **Cost:** Deploying a constellation of small satellites is more expensive than a single satellite. 
 
	 - A solution to this is what is termed as "rideshare" or "Piggyback launches". This method is very efficient as it allows multiple satellites to share the same rocket, reducing launch costs for each satellite operator. In fact, ISRO's PSLV-C37 mission set a record by launching 104 satellites into Earth's orbit in one go. We could apply something similar to this for bigger missions. For example: We could attach a couple of relay satellites when launching a satellite. The rocket could be programmed to eject each relay satellite at certain cues to ensure precise orbits of the network.
	 
	 - Since these small satellites are not going to be doing any research activity, they can be fitted with purely computation hardware to send, receive and process data.  
	 - The following Pie chart shows the weight distribution of satellite components. In a relay satellite there would be no need for a propulsion system since it is gonna hitch a ride with the main satellite. We can include thrusters so that we can have some level of control over the orbits of the satellite trajectory after deployment.
	 ![[Mangalyaan-pie-chart.png]]
	 There is also no need for Scientific instruments since the satellite is only responsible for data processing and computing.

Another idea, if it is in the realm of possibilities, could be to make use of the satellites that are have already been deployed by other countries. This will  make expensive satellite framework more accessible and also promote more collaborations between various Scientific Research agencies. Which should open the doors to the development of an interplanetary web. 

# Examples of some already implemented solutions

Right now there are multiple relay satellites in the Earth's Orbit.
- NASA also has a very efficient Mars Satellite Relay network that allows it's Mars orbital satellites and rovers to smoothly send information back and forth.

Implementing a network like this on a large scale will not only increase the efficiency of the current satellite communication system but as more missions are done and more satellites are sent into various orbits will lead to the formation of an indestructible inter-planetary network. A network like this ensures the success of future missions and even if the missions do fail, we would have access to a lot more information about the failure which is crucial to conduct other research missions and have them be successful.