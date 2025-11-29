# FreightFlowAI App

A robust Flutter application for the FreightFlowAI logistics platform, built with **Clean Architecture** and **Riverpod**.

## 🚀 Getting Started

This project uses **FVM (Flutter Version Management)** to ensure all developers use the exact same Flutter version.

### Prerequisites

#### 🪟 Windows

1.  **Install Chocolatey** (if you haven't already):
    Run in PowerShell (Admin):
    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
    ```

2.  **Install FVM**:
    ```powershell
    choco install fvm
    ```

3.  **Enable Developer Mode** (Recommended):
    *   Go to Windows Settings -> **Privacy & security** -> **For developers**.
    *   Turn on **Developer Mode**.

#### 🍎 macOS

1.  **Install Homebrew** (if you haven't already):
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2.  **Install FVM**:
    ```bash
    brew tap leoafarias/fvm
    brew install fvm
    ```

### 🛠️ Project Setup

1.  **Clone the repository**:
    ```bash
    git clone <your-repo-url>
    cd FreightFlowAI_app
    ```

2.  **Install Flutter SDK**:
    This will install the specific version pinned in `.fvm/fvm_config.json`.
    ```powershell
    fvm install
    ```

3.  **Install Dependencies**:
    Always use `fvm flutter` instead of just `flutter` to ensure you use the project's version.
    ```powershell
    fvm flutter pub get
    ```

4.  **Generate Code** (for Models/Freezed):
    ```powershell
    fvm flutter pub run build_runner build --delete-conflicting-outputs
    ```

5.  **Run the App**:
    ```powershell
    fvm flutter run
    ```

## 🏗️ Architecture

This project follows **Clean Architecture** with the following structure:

*   `lib/core`: Shared utilities, network clients, constants.
*   `lib/features`: Feature-based modules (e.g., `trips`, `drivers`).
    *   `domain`: Entities & Business Logic (Pure Dart).
    *   `data`: Repositories, DTOs, API calls.
    *   `presentation`: Widgets, Riverpod Providers.

## 📦 Key Packages

*   **State Management**: `flutter_riverpod`
*   **Navigation**: `go_router`
*   **Networking**: `dio`
*   **Data Classes**: `freezed`, `json_serializable`
