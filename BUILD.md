# Building Brogue CE

## 1. Edit Config.mk

You need these things at minimum to compile the game:

- a C compiler (Clang or GCC)
- Make

You will also need additional dependencies based on the build options you select.
You can see the options and their requirements in `config.mk`. You can configure
the build by editing `config.mk` or appending options to the Make command,
e.g. `make TERMINAL=YES`.

More specific instructions follow on how to acquire the dependencies and
build the game.

## 2. Windows Building

There are many ways to compile software on Windows. The method here was
tested by the author and is relatively simple.

### Config.mk

1. Open the file `config.mk` and set the attribute `SYSTEM := WINDOWS`

### Setting up

![image-20240116192908294](./BUILD.assets/image-20240116192908294.png)

1. Install [MSYS2][1] for x86_64. Refer to [its wiki][2] for essential info
on how to use it.

2. (Installing the dependencies) Open the `MSYS2-MSYS` shell and run the following:

    ```
    pacman -S make mingw-w64-x86_64-{gcc,SDL2,SDL2_image}
    ```

### Regular Building

![image-20240116192840473](./BUILD.assets/image-20240116192840473.png)

1. (Compiling the game) Open the `MSYS2-MINGW64` shell. Navigate to the Brogue CE
    directory (the one containing this file; your Windows drives can be accessed
    at `/c`, `/d` etc.) 
    
    ```
    cd /c/Users/Dolphin/Desktop/GIL/Project_Text2DTopDown/Brogue/
    make bin/brogue.exe
    ```



2. Optional: You can now run the game by running `cd bin; ./brogue.exe`.
    However if you want to be able to run it from outside the Mingw64 shell,
    you'll need to add the `/mingw64/bin` directory of MSYS2 to your system
    PATH. By default this is at `C:\msys2\mingw64\bin`. Some info is here:
    [How do I set or change the PATH system variable?][3] You only need to
    perform this step once.


[1]: https://www.msys2.org/
[2]: https://github.com/msys2/msys2/wiki
[3]: https://www.java.com/en/download/help/path.xml
[4]: https://brew.sh/


