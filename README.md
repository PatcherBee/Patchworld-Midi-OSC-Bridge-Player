# Patchworld-Midi-OSC-Bridge-Player
JUCE 8 Framework. This app runs a local OSC server over ipv4 and bridges pc to patchworld (vice versa). Great for DAW passthrough to Patchworld (vice versa) Allow install from unknown source and allow network access if you wish to install the .exe to start without building app yourself. (local ip only). More to come when ready! Requires Projucer (JUCE v8.0.12 used) &Ableton Link repository https://juce.com/ - https://github.com/juce-framework/JUCE - https://github.com/Ableton/link - Requires CMake to build (cmake version 4.2.1 used).

How to Build (PowerShell Terminal):

Navigate to the project folders directory (right click copy as path), 

cd (your path to folder here) - 

Remove-Item -Recurse -Force build; mkdir build; cd build; cmake ..; cmake --build . --config Release


- How To Get Connected in PatchWorld - 

For PC>Patch:
Spawn Execute block and set: port_in 3330, then hit Connect in app. (NOTE - Spawn & connect an Onload to send a jolt to set port(s) upon loading)

For Patch>PC
Spawn Execute block and set: port_out 5550, then hit Connect in app. (NOTE - Spawn & connect an Onload to send a jolt to set port(s) upon loading)

If it fails to send messages from PC to Patch, manually enter IPv4 of headset (or target device) in bridge app and reconnect. 

If still failing, add Execute block: remote_ip <IPv4 here 0.0.0.0> (NOTE - Spawn & connect an Onload to send a jolt to set ip upon loading)

If it fails to recieve messages from Patch to PC, spawn an Execute block in Patchworld and set: remote_ip <IPv4 here 0.0.0.0> (NOTE - Spawn & connect an Onload to send a jolt to activate port(s) upon loading)


IP notes:

To find IPv4 in Headset open, Settings > Network Wi-Fi > Select current Network > Scroll to find IPv4 Address

IPV4 could appear as 192.168.0.0 / 10.0.0.0 / 172.16.0.0 (will vary on router)

remote_ip should be the PC (or target device) IPv4.

Current OSC Addresses:

/chXnote
/chXnvalue
/chXnoteoff
/chXcc
/chXccvalue
/chXpitch
/chXpressure

Enable virtual keyboard and select it in MIDI IN to send OSC out to Patchworld to start playing.
-Use keys A-L (white keys), W-P black keys) Octave - Z = Down, X = Up. 
