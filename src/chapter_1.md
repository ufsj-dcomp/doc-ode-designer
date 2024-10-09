# Installation

It is recommended to use the executables available in *Releases* on GitHub. [This link](https://github.com/Syndelis/ode-designer-rs/releases/latest) can be used to always redirect to the latest version.

### Linux

The Linux distribution uses [AppImages](https://appimage.org/), which requires a runtime (`fuse2`) installable on all Linux-based distributions. It is commonly included by default by some distributions, or is already installed by another program.

<details>
<summary><b>🐧 Para Debian/Ubuntu/Pop_OS!/ElementaryOS</b></summary>

```sh
$ sudo apt install libfuse2
```

</details>

<details>
<summary><b>🐧 Para ArchLinux</b></summary>

```sh
$ sudo pacman -S fuse2
```

</details>

### Windows

The Windows distribution consists of a ZIP that can be extracted and its contents executed.

## Compilation

### Using Docker

To compile and use the software and its full potential, you can use the provided Docker image. The dependencies are only `docker` itself and the `docker-buildx` plugin.

```sh
$ docker buildx build -t ode-designer-appimage-builder .
$ docker run -v ./container-target:/ode-designer/target/ ode-designer-appimage-builder
```

After this execution, the AppImage should be available in `.container-target/appimage/ode-designer-rs.AppImage`. This AppImage, as well as those found in *Releases*, have Python and the `scipy` and `matplotlib` dependencies for code generation, interactive simulation and PDF export.

### Manually

To compile and run the software outside of the AppImage, the Rust toolchain (nightly version) is required, as well as Python >= 3.11, and the dependencies listed in `requirements.txt`. Fulfilling these requirements, simply compile like any Rust project, running

```sh
$ cargo run
```

Or 

```sh
$ cargo build --release
$ ./target/release/ode-designer-rs
```

If anything goes wrong, try 

```sh
$ git submodule update --init --recursive
$ git submodule update --recursive --remote
```

Then, recompile and run. 