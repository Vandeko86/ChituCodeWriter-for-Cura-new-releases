# ChituCodeWriter
I modified the ChituCodeWriter plugin created by Spanni26 to work with the newer versions of Cura. I don't know if the author will update it, but it seems this problem has been around for some time.

Source: https://github.com/Spanni26/ChituCodeWriter

I modified the function definition to include the `mime_type` argument and, optionally, a `kwargs` argument to capture any other unexpected arguments that Cura might pass in the future.

Changed from:
`def write(self, stream: BufferedIOBase, nodes: List[SceneNode], mode = MeshWriter.OutputMode.BinaryMode) -> bool:`

To:
`def write(self, file_name, nodes, global_container_stack, mime_type = None, **kwargs):`

The addition of `mime_type = None` and `**kwargs` ensures that the function accepts the new arguments without causing a TypeError.

Place the plugin folder inside the Cura plugins directory and restart the app.
To include the Chitu code into the gcode slice as normal an save as "Chitu gcode"

OBS: When the author updates it, I'll delete the fork.

Have Fun!
