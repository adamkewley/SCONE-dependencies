# SCONE dependencies

A project for building [SCONE](https://github.com/opensim-org/SCONE)s
dependencies for Linux.

## Usage

```bash
# optional, for clean Debian/Ubuntu machines. If you have 
# the binary dependencies already (see script), you can just
# get the submodules with `git submodule update --init --recursive`
./linux_1_get-dependencies

# build each dependency from source
./linux_2_build

# package into final tarball that the main SCONE project uses
./linux_3_package
```

## Artifacts

Currently produces a single binary tarball with the following
contents:

```text
SCONE-dependencies-<version>/
    opensim3-scone/
        <output from 'make install' for opensim3-scone>
    simbody/
        <output from 'make install' for simbody>
    OpenSceneGraph/
        <output from 'make install' for OpenSceneGraph>
```

SCONE uses the binaries in this tarball to build + package SCONE for
Linux distros. The reason this is done out-of-tree (from SCONE) is
because these dependencies can take a *very* long time to build, but
rarely change.
