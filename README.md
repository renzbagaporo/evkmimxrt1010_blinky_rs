## Building

```
cargo build
```


## Flashing

```bash
cargo embed --chip=mimxrt1010
```

## Debugging

```json
{
    "version": "0.2.0",
    "configurations": [
      {
        "type": "probe-rs-debug",
        "request": "launch",
        "name": "probe_rs Executable launch example",
        "cwd": "${workspaceFolder}",
        "runtimeExecutable": "probe-rs",
        "runtimeArgs": ["dap-server"],
        "chip": "MIMXRT1010",
        "probe": "1366:0101:000801021355",
        "flashingConfig": {
          "flashingEnabled": false,
          "haltAfterReset": false,
          "formatOptions": {
          }
        },
        "coreConfigs": [
          {
            "coreIndex": 0,
            "programBinary": "${workspaceFolder}/target/thumbv7em-none-eabihf/debug/evkmimxrt1010_blinky_rs",
            "svdFile": "${workspaceFolder}/MIMXRT1010.svd"
          }
        ],
        "env": {
          "RUST_LOG": "info"
        },
        "consoleLogLevel": "Console"
      }
    ]
}
```