# Yonah Ground Control Station (GCS)
Yonah GCS aims to be a ground control station for monitoring and controlling multiple unmanned aerial vehicles in **resource-constrained computing environments** which can be any combination of:
1. Limited Internet connectivity
2. Slow and/or unreliable computing infrastructure
3. Lack of computer literacy for local GCS operators

and more.

This GCS attempts to address the problem of locals in a third-world country having to operate a ground control station for multiple aircraft that may be delivering medical cargo or other equipment/supplies while possibly not having the technical expertise or computing literacy to use existing ground control stations. 

## Design Goals

Based on our initial descriptions:

| Goal | Details | 
| --- | --- |
| All text must be easily translatable | We expect many local languages to be used for the same GCS software. Internationalization must be built into the initial design of this software. | 
| The MSS (Main Success Scenario*) flow must be extraordinarily easy to follow | Many operators are not likely to be computer-literate. The UI/UX design must have a straightforward flow for at least the MSS of the application. |
| There should be multiple pages of progressively increasing complexity/feature access in the GCS | If the MSS does not occur (in this context - some issue with the aircraft, like a , needs to be resolved) there should be ways to incrementally view more detail and access more settings on the aircraft. This should correspond with how much the problem needs to be escalated, a.k.a a remote specialist engineer should be able to make any modifications that are required 
| Basic troubleshooting instructions should automatically appear and be easy to follow | If the MSS does not occur and the problem is common and simple to address (needs accelerometer or compass calibration / reboot / just wait longer for GPS lock etc) the troubleshooting instructions should be very clearly displayed on the GCS interface. 
| Advanced troubleshooting information should be clearly presented and instructions on how to escalate the problem should be shown | If a problem is too serious to be dealt with by the operator, troubleshooting information like a set of data to copy and paste to a remote engineer, and instructions on how to do so, should be clearly displayed
| Data from multiple aircraft in flight must be clearly displayed (e.g. v2track.com) | As this particular GCS station scales to have multiple aircraft in flight, the GCS should be able to clearly display multiple aircraft on the same map while displaying basic flight information on each of them.
| The RAM / disk / CPU usage should be kept low | The most likely type of computer to be deployed is a cheap laptop in perhaps the 300 USD range in our case. Resource usage should be kept quite low to respect this. 
| The network bandwidth required for this application should be kept as low as necessary | In rural areas in our use case, the best uplink is a 5 KBps total satellite link. The application should not tax these types of links inordinately, but should be able to scale to higher bandwidth links if installed.


*The Main Success Scenario (MSS) in this case might be: user clicks on destination and weight of cargo, waits for all lights on screen to turn green, then presses "arm and takeoff".
