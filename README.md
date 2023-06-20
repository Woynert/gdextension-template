# How to run

Install all the [dependencies needed](https://docs.godotengine.org/en/stable/contributing/development/compiling/index.html), you can use the provided [Nix script](https://github.com/Woynert/gdextension-template/blob/f8c5b55d9c052b47fb1b79aa4b9d313d25e530ed/shell.nix) to automatically create a shell with everything needed:

```
$ nix-shell
```

Clone the repo including submodules:

```
git clone --recurse-submodules https://github.com/Woynert/gdextension-template demo 
```

Extract the extension_api.json from your godot binary:

```
cd godot-cpp
godot4 --dump-extension-api extension_api.json
```

Compile the godot bindings with scons:

```
cd godot-cpp
scons platform=<platform> -j4 custom_api_file=./extension_api.json
```

Compile the gdextension (Run from the project's root):

```
scons platform=<platform>
```

Now you can run the godot game through the editor.

