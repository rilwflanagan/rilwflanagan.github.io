---
layout: page
title: PROJECT PORTFOLIO
---
Riley W. Flanagan  
M.S. Computer Science - Georgia Institute of Technology  

***


Thank you for taking an interest in my work! This portfolio is meant to provide a snapshot of my skillset and the type of projects I've been in engaged in over the course of my career.  

If you're interested in further details, I can be reached at <rilwflanagan@gmail.com>.

## ***SILENT SPEECH INTERFACES FOR AUGMENTED REALITY***
Lead investigator on university-funded research into subvocal communication schemes utilizing non-invasive EMG electrodes on the surface of the neck. EMG data was filtered and used to train a classifier network built in Python with Keras as a command interface for Augmented Reality devices. I authored a procedure set for collection of data from human participants and received permission from the institutional review board to work with them in the lab. Results were published through the Computer Methods in Biomechanics and Biomedical Engineering conferefence:
> C. D. Walck, R. Flanagan, and T. Rivas, “Development of a Silent Speech Interface for Augmented Reality Applications,” 2021 CMBBE Symposium

![Sensor Placements!](Fig1.png "Sensor Placements")  
*Final sensor placements after downselection of viable positions.*

![Segmentation!](segmentation.JPG "Segmentation")  
*Example EMG recording of the mouthed and subvocalized command "Right" over three trials.*

*Note: Both data and subject images shown above are my own from preliminary testing, and were not sourced from study participants.*

## ***NASA S.U.I.T.S. DESIGN CHALLENGE***
Designed and prototyped an astronaut heads-up-display (HUD) utilizing the augmented-reality (AR) MagicLeap platform to display mission objectives, livestream suit vital data, navigate a lunar environment, and provide note-taking capabilities as part of the NASA SUITS design challenge. The team’s design was tested live in a simulated Mars analog at Johnson Space Center. As part of a 5-person team, I primarily developed the Vitals Screen that fetched data from a continuous backend telemetry stream in C# using Unity. Various simulated errors can be triggered via a backend control center to notify the astronaut of low oxygen, fan errors, pressure leaks, and more. Navigation elements I contributed to include live mapping, a dynamic visual waypoint system, and route adjustment with obstacles. The result is a fluid interface for astronauts that enables autonomy. Results are published in IEEE:
> L. S. Miller, M. J. Fornito, R. Flanagan and R. L. Kobrick, "Development of an Augmented Reality Interface to Aid Astronauts in Extravehicular Activities," 2021 IEEE Aerospace Conference (50100), 2021, pp. 1-12

![img_1.png!](img_1.png "Pathing")  
*Real-time navigation capability with live pathing as seen through the MagicLeap.*

![navmap.png!](navmap.png "Segmentation")  
*Calibrated map screen with position, path, several waypoints, and destination.*

![vitals.png](vitals.png "Vitals")  
*Vitals screen with live datapoints shown, streamed from lander telemetry.*

## ***MULTI-PROCESS DISTRIBUTED FILE TRANSFER SYSTEM***
Developed a multi-process client-server file transfer system in C to synchronize directories on a single machine with multithreaded operation on shared memory
for a class project. The flow of control involved three major processes: a client who could request a file via HTTP
web request, a webproxy who would receive client requests and allocate IPC resources to retrieve remote data from
cache, and a cache daemon that used a boss-worker multithreading pattern to assign threads to deliver requested files
back to the webproxy and through to the client. The webproxy and cache daemon interfaced through a
pool of reusable shared memory segments, message queues shared request
information, and per-segment semaphores were used to pace data transmission into chunks so the webproxy
could maintain a low memory footprint. POSIX thread usage enabled many concurrent requests for files to be handled at once.

I later iterated by refactoring the system with C++ to include a robust gRPC based API instead of shared memory segments. Clients can call standard methods to add, fetch, and delete files stored in the server cache.
The server is used to actively synchronize files between all clients, and can check their directories and update them with gRPC calls defined earlier.
Server-managed locks enable thread-safe concurrency so many clients can execute calls simultaneously. The completed product is an operating system component that can synchronize data in a performant manner for many different applications.

![Flowofcontrol.png](Flowofcontrol.png "Vitals")  
*Flow of control schematic of the file transfer system.*
