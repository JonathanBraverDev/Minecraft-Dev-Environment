# Minecraft Development Environment

This repository manages the infrastructure for Minecraft plugin development. It provide a structured workspace and shared build logic.

## Prerequisites
- **Java 25 JDK** (installed and in your `PATH`)
- **GitHub CLI (`gh`)** (recommended for managing plugin repositories)

## How to Set Up the Environment
1. **Clone this repository** to your machine:
   ```powershell
   git clone https://github.com/JonathanBraverDev/Minecraft-Dev-Environment .
   ```
2. **Set up the server**:
   Run the setup script to download the latest PaperMC server and configure it:
   ```powershell
   ./scripts/setup-server.ps1
   ```

## How to Add Plugins
To add a new or existing plugin to this environment, clone it into the `plugins/` folder. Compatible plugins use the shared infrastructure located in `scripts/plugin-common.gradle`.

### Example: Adding the Template Repository
If you want to start a new project from your template:
1. **Navigate to the plugins folder**:
   ```powershell
   cd plugins
   ```
2. **Clone the repository**:
   ```powershell
   gh repo clone JonathanBraverDev/Minecraft-Plugin-Template
   ```
3. **Build and Deploy**:
   Since the template already uses the shared logic, it "plugs in" immediately:
   ```powershell
   cd Minecraft-Plugin-Template
   ./gradlew build
   ```

## Workflow
1. **Develop** your plugin in its folder inside `plugins/`.
2. **Deploy** by running `./gradlew build` (or `./gradlew deploy`). This automatically copies the JAR to `/server/plugins/`.
3. **Run** the server using `server/start.bat`.

## Directory Structure
- `/plugins/`: Container for individual plugin repositories.
- `/scripts/`: Shared build infrastructure (`plugin-common.gradle`) and setup scripts.
- `/server/`: Local PaperMC server (git-ignored, managed by scripts).
