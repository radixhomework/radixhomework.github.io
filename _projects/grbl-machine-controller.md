---
title: "GRBL Machine Controller"
order: 4
status: "Tools"
short_description: "A Python desktop application to control a GRBL-based CNC machine."
image: "/assets/images/grbl-machine-controller-logo.png"
image_alt: "GRBL Machine Controller logo"
---

## About

GRBL Machine Controller is a Python desktop application built to drive a
personal GRBL-based CNC machine. It connects to the controller board over
serial and puts the essential day-to-day controls in one place: manual
jogging, G-code job streaming, and probing with tool diameter
compensation.

The machine can also be watched from the rest of the house: a built-in
Home Assistant integration over MQTT automatically exposes sensors
(status, position, RPM, progress), buttons and override controls through
MQTT discovery, so the CNC shows up in Home Assistant without extra
configuration.

## What is here?

- Manual jogging and G-code job streaming over serial
- Probing with tool diameter compensation
- Home Assistant integration via MQTT auto-discovery
- Built-in simulator mode (`--fake`) that works without hardware
- Qt (PySide6) user interface
- Runs on a Raspberry Pi (systemd service included) or any machine with
  Python 3.9+, including Windows and WSL2

## Work in progress

GRBL Machine Controller is under active development. Source code and
documentation live on GitHub:
[radixhomework/grbl-machine-controller](https://github.com/radixhomework/grbl-machine-controller).
