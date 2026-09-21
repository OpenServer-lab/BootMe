# BootMe

**A simple, direct disk-image flasher written in Fly.**

BootMe is a native-compiled disk imaging utility designed to make writing `.iso`, `.img`, and other disk images to removable drives straightforward.

It is built with the [Fly programming language](https://fly-lang.com/) and aims to keep the application logic simple, explicit, and easy to understand.

> **Flash the image. Verify the result. Don't make it complicated.**

## Why was this made when tools like Rufus already exist?

Because I kept trying them.

BootMe started after using tools such as **Rufus**, **Win32 Disk Imager**, **Ventoy**, **Etcher**, and even `dd` for the simple job of putting an image onto a drive.

They all work. That's not the problem.

The problem was that, at least for the way I wanted to work, disk imaging kept turning into a choice between:

* a GUI with a lot of options and behavior I didn't need,
* a tool with a workflow designed around boot media creation rather than simply writing an image,
* or a command-line utility where one wrong argument can become a very bad afternoon.

So BootMe became an idea:

> **What if I just made the stupidly simple disk flasher I wanted?**

That is also why BootMe is written in **Fly**. This is partly a practical project and partly a demonstration of what Fly can actually be used to build.

BootMe isn't trying to prove that Rufus is obsolete. It exists because sometimes the best way to get the exact tool you want is to make it yourself.

## Features

* 🖥️ Native graphical interface
* 💿 Disk-image flashing
* 🔍 Byte-for-byte verification
* ⛔ Flash cancellation
* 📦 Chunked image writing
* 📏 Handles targets larger than the source image
* 🧪 Deterministic file-backed testing
* 🪟 Windows-native device access
* ⚡ Compiled natively with Fly + LLVM

## The Goal

BootMe is built around a small workflow:

```text
Select image
     ↓
Select target
     ↓
Flash
     ↓
Verify
     ↓
Done
```

The important behavior should be obvious.

No giant wizard.
No unnecessary configuration maze.
No pretending that writing an image to a disk needs to be mysterious.

## Verification

BootMe does not simply assume that a successful write means the device is correct.

After flashing, BootMe verifies the written image against the target device byte-for-byte.

The verification logic intentionally compares **only the image span**.

For example:

```text
Image:   160000 bytes
Target:  160160 bytes

┌──────────────────── Image ────────────────────┐
0                                      159999
└───────────────────────────────────────────────┘
                                        ┌── Target tail ──┐
                                        160000      160159
```

The extra bytes on the target are not treated as an error.

However, corruption anywhere inside the image's 160000-byte span is still detected.

This behavior is covered by the deterministic BootMe engine test harness.

## Testing

BootMe includes a file-backed engine test harness so the flashing state machine can be tested without requiring a physical disk.

The harness exercises:

* Empty image rejection
* Normal flashing
* Verification
* Independent whole-file comparison
* Corruption detection
* Targets larger than the image
* Corruption inside the image span of a larger target
* Cancellation
* Size formatting

The larger-target test is especially important because a real block device is normally larger than the image being written.

The test harness uses ordinary files as virtual devices, making the behavior reproducible without risking an actual disk.

## Project Structure

```text
bootme/
├── bin/
├── src/
│   └── main.fly
├── module/
│   ├── engine.fly
│   ├── engine_test.fly
│   └── engine_test.expected
└── flylink.sleep
```

### `src/main.fly`

BootMe's application and GUI entry point.

### `module/engine.fly`

The GUI-independent flashing state machine.

This contains the core flashing and verification logic.

### `module/engine_test.fly`

Deterministic, file-backed end-to-end tests for the flashing engine.

### `flylink.sleep`

The Fly project manifest.

## Built With

BootMe is written primarily in **Fly**.

The project uses native runtime functionality where operating-system primitives are required, such as:

* Block-device access
* Device enumeration
* File operations
* GUI primitives
* Event handling

Application logic remains in Fly rather than being implemented as a large C/C++ application with a Fly wrapper.

## Building

BootMe requires a working Fly toolchain.

Build the project with:

```text
fly -build
```

### Running

BootMe requires **administrator elevation** because it accesses physical storage devices.

Consequently, the normal:

```text
fly -run
```

workflow is **not sufficient for BootMe** on Windows.

The project's `flylink.sleep` manifest requests the required Windows elevation behavior so that the built application can run with the permissions needed for raw device access.

For development and testing, use the generated executable through the appropriate elevated Windows launch path.

The file-backed engine test harness does **not** require a physical disk and should be used for deterministic development testing.

## Safety

**Be careful when selecting the target device.**

Writing an image to a physical device can destroy the existing data on that device.

Before using BootMe with real hardware:

1. Confirm the selected image.
2. Confirm the selected target.
3. Make sure the target contains no data you need.
4. Never assume the device number or name is correct.
5. Keep important data backed up.

The file-backed test harness should be used during development before testing against physical hardware.

## Requirements

* A working Fly toolchain
* Windows for the current physical-device flashing path
* Administrator privileges when accessing physical storage devices

The project is structured around Fly's cross-platform toolchain, while operating-system-specific device access is implemented through the appropriate native runtime layer.

## Status

BootMe is under active development.

The flashing engine's deterministic verification milestone covers the important edge case where:

> **target size > image size**

and confirms that:

* A larger target can verify successfully.
* The unused target tail does not cause a false verification failure.
* Corruption within the written image region is still detected.
* Cancellation works.
* Empty images are rejected.

GUI integration, Windows subsystem/elevation support, packaging, and remaining release work are being developed around that engine.

## Philosophy

BootMe is intentionally small in concept:

> **Pick an image. Pick a disk. Flash it. Verify it.**

No unnecessary abstraction should get in the way of those four steps.

## License

BootMe is released under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.

---

**BootMe — disk flashing without the ceremony.**
