
# Introduction #
This project is a simulation of an ant colony using **artificial intelligence with the NEAT algorithm (NeuroEvolution of Augmenting Topologies)**.  
It was developed as a 2nd-year engineering school project at **Polytech Dijon** by:  
- **Yohann Turpin**  
- **Lauric Géhu**
- 
The simulation allows agents (ants) to evolve over time to improve their behavior and decision-making.  
👉 A playable **release** is available where ants can find their way through a maze.

# Compilation Instructions
Several steps are required to compile the project.
### 1. Install Dependencies
- Download **[Raylib 5.0](https://github.com/raysan5/raylib/releases/tag/5.0)**  
- Download **[Raygui 4.0](https://github.com/raysan5/raygui/releases/tag/4.0)**  
- Extract both at the root of your system drive, preferably at `C:\`.  

Move the file `raygui.h` into:  `C:\raylib\raylib\src`

Par la suite, il faut modifier des macros dans le fichier `C:\raylib\raylib\src\config.h`.
Les deux macros suivantes doivent être mis en commentaire: 


### 2. Configure Raylib
In the file `C:\raylib\raylib\src\config.h`, edit the macros as follows:

- Comment out:
```c
#define SUPPORT_PARTIALBUSY_WAIT_LOOP 
#define SUPPORT_BUSY_WAIT_LOOP  
```
- Uncomment:
```
#define SUPPORT_CUSTOM_FRAME_CONTROL 
```

3. Compile Raylib

From the src folder of Raylib, run:
```bash
MAKE
```

4. Configure VSCode

To compile and run the project with Visual Studio Code:

1. Go to:  
`C:\raylib\raylib\projects\VSCode\`  
2. Copy the `.vscode` folder into the root of your project.
3. Edit `tasks.json` and update the "args" section as follows:

```json
"args": [
            "RAYLIB_PATH=C:/raylib/raylib",
            "PROJECT_NAME=${workspaceFolderBasename}.exe",
             "OBJS=src/*.cpp",
            "BUILD_MODE=DEBUG"
          ]
```

# Running the Simulation

Once compiled, launch the executable.

Ants will be simulated in their environment.

With each generation, behaviors evolve using NEAT.

In the latest release, ants are able to navigate and find their way through a maze.

#  References

- [Raylib Documentation](https://www.raylib.com/)  
- [NEAT Algorithm (Stanley & Miikkulainen, 2002)](http://nn.cs.utexas.edu/downloads/papers/stanley.ec02.pdf)
