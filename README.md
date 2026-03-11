# Minecraft Development Environment

This repository manages the infrastructure for Minecraft plugin development. It provides a structured workspace and shared build logic.

## Prerequisites
- **Java 25 JDK** (installed and in your `PATH`)
- **GitHub CLI (`gh`)** (for managing plugin repositories)

## How to Replicate This Setup
1. **Clone this repository** to your machine:
   ```powershell
   git clone https://github.com/JonathanBraverDev/Minecraft-Dev-Environment .
   ```
2. **Setup the server**:
   Run the setup script to download the latest PaperMC server and configure it:
   ```powershell
   ./scripts/setup-server.ps1
   ```
3. **Clone your plugins**:
   Clone your plugin repositories into the `projects/` folder:
   ```powershell
   cd projects
   git clone [Your-Plugin-Repo-URL]
   ```
4. **Build and Deploy**:
   Since the build logic is shared, you can build your plugin from its folder, and it will automatically deploy to the local server:
   ```powershell
   cd [Plugin-Folder]
   ./gradlew build
   ```

## Directory Structure
- `/projects/`: Individual plugin source repositories.
- `/scripts/`: Shared build infrastructure (`plugin-common.gradle`) and setup scripts.
- `/server/`: Local PaperMC server (automatically managed by scripts).
