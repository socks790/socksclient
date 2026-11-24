SOCKS CLIENT (Fabric, Minecraft 26.3)
Draws a Lunar-style "SOCKS CLIENT" watermark (dark panel + sock logo) in the bottom right of the HUD and every screen.
The watermark image is assets/socksclient/textures/gui/watermark.png (177x40) - swap it for your own art; if you change its size, update TEX_W/TEX_H in SocksClientMod.java.

BUILD THE JAR (pick one)
A) No install: make a free GitHub repo, upload this folder's contents
   (including the hidden .github folder), open Actions > build > Run workflow,
   then download the "socksclient-jar" artifact.
B) Local: install JDK 25 + current Gradle, run:  gradle build
   Jar: build/libs/socksclient-1.0.0.jar  (not the -sources one)

INSTALL: put the jar + Fabric API (26.3) in your mods folder. Fabric Loader 0.19+.
