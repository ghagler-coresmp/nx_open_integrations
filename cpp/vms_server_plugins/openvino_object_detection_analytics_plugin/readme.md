# OpenVINO Object Detection Analytics Plugin

This is an open-source example plugin for Nx Meta demonstrating people detection and tracking. It
may or may not fulfil the requirements of the particular video management system in terms of
reliability and detection quality - use at your own risk. It is based on OpenVINO technology by
Intel, and runs on Intel processors only.

For general information about building and installing Plugins for Nx Server, see `readme.md` in the
Nx Metadata SDK.

## License

This software is licensed under Mozilla Public License Version 2.0 uses third party libraries that
are distributed under their own terms (see `LICENSE-3RD-PARTY.txt`).

## Building

This example can be compiled either for Linux, or for Windows.

### Build environment

- C++17 compiler; tested with GCC 7.4 and MSVC 14.2

- CMake 3.16 or later

- patchelf (for Linux only)

- Intel OpenVINO; tested with versions:
    - Windows: 2020.1.033
    - Linux: 2020.1.023
    
- Nx Metadata SDK; tested with version metadata_sdk-4.1.0.32024 which is intended for creating
    plugins targeted for Nx Meta 4.1 (such plugin binaries will work with later Nx Meta versions)

- Boost: boost-1.66.0 or later

### Build steps

```
cmake -B <build_dir> <src_dir> -DCMAKE_BUILD_TYPE=Release -DmetadataSdkDir=<unpacked_zip_dir>
cmake --build <build_dir> --config Release --target openvino_object_detection_analytics_plugin_zip
```

On success, the built plugin appears in the following directory:
```
<build_dir>/cpp/vms_server_plugins/openvino_object_detection_analytics_plugin/openvino_object_detection_analytics_plugin.zip
```

To install the Plugin, unpack the above zip to a dedicated directory that you need to create:
`<nx_server_installation_dir>/bin/plugins/openvino_object_detection_analytics_plugin/`.
