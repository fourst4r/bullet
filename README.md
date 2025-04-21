# Bullet

[Bullet Physics](https://github.com/bulletphysics) wrapper for Heaps

Supports both HashLink and JS output thanks to [WebIDL](https://github.com/ncannasse/webidl)

## Instructions for building for HL on Windows

1. Set up the environment
```
git clone https://github.com/nspitko/bullet.git
git clone https://github.com/bulletphysics/bullet3.git ./bullet/src/bullet
haxelib dev bullet bullet
haxelib git webidl https://github.com/nspitko/webidl.git
```

2. Generate the HL shim
```
cd bullet
haxe -lib webidl --macro "bullet.Generator.generateCpp()"
move bullet.cpp src/
```
	
3. Open bullet.sln (if it asks you to upgrade toolset, click OK). Press `Ctrl+Shift+B` and wait for it to build.

4. Copy the generated bullet.hdll from x64/Release or x64/Debug into your HashLink folder with the other hdlls.

5. Optional: Test if it works by running `haxe build.hxml -lib heaps -lib hldx --cmd dummy.hl`

TODO: instructions for JS as well

