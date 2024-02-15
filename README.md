# jojo

Jojo comprises various components that collectively form a system enabling control of peripherals from a host PC via a WiFi network.

### Quick Links

- [Getting Started](#getting-started)
- [Usage](#usage)
- [Roadmap](#roadmap)
- [License](#license)

## Getting Started

This project originated as a means to explore the [Rust programming language](https://www.rust-lang.org/). It enabled the creation of a backend ([jojo-server](https://github.com/gggiulio77/jojo-server)), a frontend ([jojo-app](https://github.com/gggiulio77/jojo-app)), and an embedded application ([jojo-client](https://github.com/gggiulio77/jojo-client)), all within the Rust ecosystem, utilizing frameworks, tools, and more.

Here's a brief summary of each repository:

- [jojo-client](https://github.com/gggiulio77/jojo-client): An embedded app utilizing the [esp32s3](https://docs.espressif.com/projects/esp-idf/en/stable/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1.html) development board, serving as a WiFi "remote control". Developed using the [Espressif Rust ecosystem](https://github.com/esp-rs).
- [jojo-common](https://github.com/gggiulio77/jojo-common): A library serving as a centralized location for business models and driver implementations to control peripherals, utilized across the entire project.
- [jojo-server](https://github.com/gggiulio77/jojo-server): A WebSocket server built with [Axum](https://github.com/tokio-rs/axum), serving as the network layer between the [jojo-client](https://github.com/gggiulio77/jojo-client) and the host PC.
- [jojo-discovery](https://github.com/gggiulio77/jojo-discovery): A UDP socket tasked with replying to broadcast messages with local network information of the host PC. Used by the [jojo-client](https://github.com/gggiulio77/jojo-client) to locate [jojo-server](https://github.com/gggiulio77/jojo-server).
- [jojo-app](https://github.com/gggiulio77/jojo-app): A desktop application serving as the user's entry point. It deploys [jojo-server](https://github.com/gggiulio77/jojo-server) and [jojo-discovery](https://github.com/gggiulio77/jojo-discovery) on the host PC and provides a GUI to manage all connected clients. Developed with Tauri and Leptos.
- [jojo-otp-app](https://github.com/gggiulio77/jojo-otp-app): Another desktop application designed to offer users a user-friendly way to save network credentials (WiFi SSID and password) in [jojo-client](https://github.com/gggiulio77/jojo-client). Developed with Tauri and Leptos.
- [jojo-wifi-manager](https://github.com/gggiulio77/jojo-wifi-manager): A library utilized by [jojo-otp-app](https://github.com/gggiulio77/jojo-otp-app) to connect to the network of [jojo-client](https://github.com/gggiulio77/jojo-client) using the OS's WiFi module.

## Usage

- Requirements: To use Jojo, you need a PC running Windows and an [esp32s3](https://docs.espressif.com/projects/esp-idf/en/stable/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1.html) board.

- Visit [jojo-client](https://github.com/gggiulio77/jojo-client) and download the binary from a release tag. Flash it to the board using [espflash](https://github.com/esp-rs/espflash). The board will appear as an access point (AP), allowing you to store your WiFi network credentials.

- Head to [jojo-otp-app](https://github.com/gggiulio77/jojo-otp-app) and download the installer from a release tag. Install the application and connect to the client's WiFi network. Follow the app's instructions to enter your SSID and password.

- Navigate to [jojo-app](https://github.com/gggiulio77/jojo-app) and download the installer from a release tag. Open the app and customize the client buttons according to your preferences.

## Roadmap

- [ ] Improve documentation with diagrams, videos, etc.

## License