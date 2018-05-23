---
layout: post
title:  "Midair Hotswap"
author: "Trey Fortmuller"
date:   2017-06-15
excerpt: "A mechatronics platform designed to autonomously swap a quadcopter's battery, without touching the ground."
image: "/images/hotswap/main1.jpg"
---

## Introduction

The Midair Hotswap is a project I did within the UAVs@Berkeley student organization campus at Cal which I now lead as President. I began this project at the start of my Sophomore year as a Team Lead. We started with about 12 people and over the course of the 3 semesters we worked on this project, we ended up with a team of 5 dedicated undergraduate engineering students who stuck it out till the bitter end. This project was incredibly rewarding to work on. Not only did my technical knowledge, prototyping intuition, and design methodology strengthen over the course of the 3 semesters, my understanding of how to work in a team grew enormously. From simple face to face communication on technical topics, to delegating tasks that play to the strengths of each team member, to maintaining a unified vision, and even keeping my team motivated and inspired to pursue this project, I couldn't have asked for a better platform to grow as a future professional engineer.

## Motivation

In response to growing popularity in UAVs, drone manufacturers and developers are increasingly putting efforts into improving the performance and capabilities of their products. One of the most important metrics for multirotor performance is flight time, how long the vehicle can stay in the air before its battery depletes. The longest flight time among consumer UAVs only reach up to half an hour. Researchers across the globe are seeking to improve battery chemistries and UAV flight efficiency. The Midair Hotswap project approaches this problem from another angle, replacing the battery of a drone with a new one, without touching the ground.

## Project Description

The Midair Hotswap consists of two UAVs. One larger hexacopter and a smaller quadcopter. The small quadcopter lands on top of the larger hexacopter while both are hovering the air. Mechatronics on board the landing platform which rests on top of the hexacopter then swap out the battery of the quadcopter. The quadcopter can then take off again with a fully charged battery, having never landed on the ground to get its battery replaced.

<span class="image main"><img src="{{ "/images/hotswap/full.png" | absolute_url }}" alt="" /></span>

### Subsystems

<div class="table-wrapper">
	<table>
		<tbody>
			<tr>
				<td nowrap><b>Quadcopter</b></td>
				<td>The target of our battery swap. Runs the Betaflight firmware on a Naze32 flight controller. 3D printed cones secure to the motor mounts and the battery slides into the underside of drone.</td>
			</tr>
			<tr>
				<td nowrap><b>The Hexacopter</b></td>
				<td>The large payload carrier which hovers our landing platform and swapping system. It runs iNavigation firmware on an SPF3 Mini flight controller and can autonomously loiter.</td>
			</tr>
			<tr>
				<td nowrap><b>Battery case and interface</b></td>
				<td>A hobbyist LiPo battery fits inside a case which exposes its power leads on flat copper plates. This case slides into the quadcopter interface which powers the drone from the battery via spring loaded contacts. The battery is locked inside the interface during quadcopter flight by an interference joint.</td>
			</tr>
			<tr>
				<td nowrap><b>Landing platform</b></td>
				<td>The laser cut wooden platform which rests on top of the hexacopter and the “megaphone” cones which guide the quadcopter into the correct position every time it lands.</td>
			</tr>
			<tr>
				<td nowrap><b>Linear slide rig</b></td>
				<td>Consisting of chrome rods, linear bearings, a stepper motor and battery carriage, this automated system carries out the battery swap. An Arduino controls the rig and end stop switches placed in the 3D printed mounts for the chrome rods allow us to calibrate the motion of the carriage before every swap.</td>
			</tr>
		</tbody>
	</table>
</div>

## Challenges

#### Battery case and latch mechanism

<span class="image right"><img src="{{ "/images/hotswap/batt.png" | absolute_url }}" alt="" /></span>

The main challenge here was finding the right balance between simplicity (minimal motors) and the security of the locking mechanism during flight. We solved this with an interference joint on our battery case to lock it perfectly in place.

#### Swapping mechanism
We use a linear sliding rail to push out the old battery case and simultaneously slide in a new one. This requires only one stepper motor and 2 limit switches for precision alignment. The automation of the swapping is handled by an Arduino Uno. One current limitation of the approach is not being able to perform more than one battery hotswap for a single flight of the hex. We considered designing battery magazines that carry many batteries at once but decided to skip this feature for our proof of concept.

#### Landing guidance system
We initially designed an autonomous guidance system using OpenCV SURF Feature detection, but then transitioned to supporting hardware guidance to allow for manual landing. The “megaphone” scoops allows for easier precision landing.

#### Electronics
To facilitate a reliable battery connection, we used copper plates on the battery case as an interface to the battery itself. The battery interface on the quadcopter has 4 10-prong spring loaded contact pins for dynamically adjusting to the location and height of each copper plate on the battery case. These are then directly wired to the quad.

## Design Approach
The system was designed with a bottom up strategy in which each independent system (i.e. hex, quad, linear slider) was designed independently while maintaining an overall grasp on the the final goal. Components that interface with two or more subsystems were designed in the full assembly. The main goal of the project was a successful battery swap, which is mostly a mechatronics design problem. We found design inspiration for the critical mechanisms from plastic buckles to hair clips to leaf springs. Throughout the development process, constant attention was given to designing parts and systems that could utilize rapid prototyping techniques and facilities on campus. All CAD was done through Autodesk Fusion 360 using multiple assemblies to produce complex systems to ideate and develop unique solutions to the problems at hand. All parts that were fabricated with off the shelf parts were transferred by hand into Fusion to streamline the design process.

<span class="image main"><img src="{{ "/images/hotswap/linear_slider.png" | absolute_url }}" alt="" /></span>

## Prototyping

<span class="image left"><img src="{{ "/images/hotswap/cases.jpg" | absolute_url }}" alt="" /></span>

Iterating on each design was done through rapid prototyping techniques including 3D printing, laser cutting, and waterjet cutting. 3D printing was used throughout the build for custom parts with a more complex geometry. The vast majority of prints were completed on desktop FDM printers including Type As and Printrbots. The battery cases and interference joints required higher dimensional accuracy, those were printed from ABS on a Stratasys Fortus printer. 3D printing can be difficult to use, has inherent flaws, and publicly available desktop FDM machines on campus fail frequently. Though these machines can be frustrating, the frequency with which they allowed us to iterate on parts with complex 3D geometry was a huge asset to our project and the progress of our mechanical design.

## Project Poster
To finish off the project, the team and I designed this poster to hang in the UAV lab on campus. We'll display the project to hopefully inspire future generations of UAVs@Berkeley students to try something equally ambitious.

<span class="image main"><img src="{{ "/images/hotswap/poster.png" | absolute_url }}" alt="" /></span>

### The Team

<span class="image main"><img src="{{ "/images/hotswap/team.jpg" | absolute_url }}" alt="" /></span>

UAVs@Berkeley's Fall 2017 Milestone 3 event, from left to right: Suneel, Connor, Dipo, Darius, and yours truly.


