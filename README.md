# Yonah Ground Control Station (GCS)

## Description 

Yonah GCS aims to be a ground control station for **monitoring** and **controlling** multiple unmanned aerial vehicles in **resource-constrained computing environments** which can be any combination of **technical** and **social** factors like:
1. Limited Internet connectivity
2. Slow and/or unreliable computing infrastructure
3. Lack of computer / technical literacy for local GCS operators

and more.

This GCS attempts to address the problem of **locals in a third-world country** having to operate a ground control station for multiple aircraft that may be delivering **medical cargo** or other equipment/supplies while possibly **not having the technical expertise or computing literacy** to use **existing ground control stations**. The GCS should also be designed for remote troubleshooting and monitoring by the team that designed the aircraft system. 

## User Profiles
<details open>

| User | Use Case Profile | 
| ---  | --- |
| Local GCS Operator  | Should experience a straightforward flow to launch and manage aircraft, and to remedy simple issues with the aircraft if they arise |
| Local Aircraft Technician | Should be able to diagnose and fix / suggest actions to remedy problems on the aircraft on the ground and in flight |
| Level 1 authorized remote user | Should be able to view what Local GCS Operator can view without being able to make changes |
| Level 2 authorized remote user | Should be able to view and control Local GCS Operator's view | 
| Level 3 authorized remote user | Should be able to view and control Local GCS Operator's view and the Aircraft Technician view |

<summary>
Click to expand/collapse
</summary>
</details>

## Main User Views (Extracted from User Profiles)
<details open>

| Flow | Description | 
| ---  | --- |
| Local Operator View  | Able to load mission profiles, launch aircraft, make abort decisions in flight, do basic troubleshooting |
| Aircraft Technician View | Full access to all parameters of aircraft and can execute any possible command on aircraft |
| Switchable View | Able to switch between both views as necessary |

 <summary>
Click to expand/collapse
</summary>
</details>


## Design Principles

<details>

Based on our initial descriptions:

| Principle | Details | 
| --- | --- |
| All text must be **easily translatable** | We expect many local languages to be used for the same GCS software. Internationalization must be built into the initial design of this software. | 
| The **MSS** (Main Success Scenario*) flow must be extraordinarily **easy to follow** | Many operators are not likely to be computer-literate. The UI/UX design must have a straightforward flow for at least the MSS of the application. |
| There should be multiple pages of **progressively increasing complexity/feature access** in the GCS | If the MSS does not occur (in this context - some issue with the aircraft, like a sensor failure, needs to be resolved) there should be ways to incrementally view more detail and access more settings on the aircraft. This should correspond with how much the problem needs to be escalated, a.k.a a remote specialist engineer should be able to make any modifications that are required 
| **Basic troubleshooting** instructions should **automatically appear** and be easy to follow | If the MSS does not occur and the problem is common and simple to address (needs accelerometer or compass calibration / reboot / just wait longer for GPS lock etc) the troubleshooting instructions should be very clearly displayed on the GCS interface. 
| **Advanced troubleshooting** information should be **clearly presented** and instructions on how to escalate the problem should be shown | If a problem is too serious to be dealt with by the operator, troubleshooting information like a set of data to copy and paste to a remote engineer, and instructions on how to do so, should be clearly displayed
| Data from **multiple aircraft** in flight must be clearly displayed (e.g. v2track.com) | As this particular GCS station scales to have multiple aircraft in flight, the GCS should be able to clearly display multiple aircraft on the same map while displaying basic flight information on each of them.
| The **RAM / disk / CPU usage** should be **kept low** | The most likely type of computer to be deployed is a cheap laptop in perhaps the 300 USD range in our case. Resource usage should be kept quite low to respect this. 
| The **network bandwidth** required for this application should be **kept as low as possible** | In rural areas in our use case, the best uplink is a 5 KBps total satellite link. The application should not tax these types of links inordinately, but should be able to scale to higher bandwidth links if installed.


*The Main Success Scenario (MSS) in this case might be: user clicks on destination and weight of cargo, waits for all lights on screen to turn green, then presses "arm and takeoff".
<summary>
Click to expand/collapse
</summary>
</details>

## Basic problems that should trigger semi-automated troubleshooting
<details>

| Problem | Resolution |
| --------- | --------- |
| **Accelerometer re-calibration required** | Run through accelerometer calibration procedure | 
| **Compass re-calibration required** | Run through compass calibration procedure | 
| **Airspeed sensor re-calibration required** | Place hand over airspeed sensor tube and press a calibration button |
| **Battery level insufficient for flight distance** | Change batteries |
| **No GPS detected** | Check if GPS is plugged in | 
| **No GPS lock after 1 minute** | Check GPS settings and where aircraft is placed |
| **Accels/Gyros inconsistent** | Re-calibration accelerometer or restart |
<summary>
Click to expand/collapse
</summary>
</details>

## Visual interfaces
| Priority | Feature | Description |
| -------- | ------- | ----------- |



## Features Required
| Priority | Feature | Description |
| -------- | ------- | ----------- |

