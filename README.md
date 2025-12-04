# WordPress Plugin Dev Template

A production-ready DevContainer template for developing WordPress plugins. This setup isolates your environment, ensuring consistent dependencies, Xdebug configuration, and WP-CLI access without polluting your local machine.

## 📋 Requirements

* [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Running)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Dev Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) (VS Code)

## 🚀 Quick Start

1.  **Create Repository:** Click **"Use this template"** on GitHub to create a new repo, or clone this repo locally.
2.  **Open in VS Code:** Open the folder in Visual Studio Code.
3.  **Launch Container:** Click the blue/green remote icon (bottom-left) and select **Reopen in Container**.
    * *Note: The first launch takes a few minutes to build the image.*
4.  **Install WordPress:** Open `http://localhost:8000` in your browser and run through the standard 1-minute WordPress installation.

## 🛠 Project Setup

Once the container is running, personalize the plugin for your specific project:

1.  **Rename the Entry File:**
    Rename `plugin-loader.php` to your plugin name (e.g., `my-awesome-plugin.php`).
2.  **Update Headers:**
    Open the file and update the `Plugin Name` and `Description` in the file header.
3.  **Activate:**
    The container tries to activate `local-dev-plugin` automatically. Since you renamed it, run this in the VS Code terminal:
    ```bash
    wp plugin activate my-awesome-plugin
    ```

## 🔌 Access & Credentials

| Service | URL | User | Password |
| :--- | :--- | :--- | :--- |
| **WordPress** | `http://localhost:8000` | Created by you | Created by you |
| **phpMyAdmin** | `http://localhost:8080` | `root` | `root` |
| **Database** | Host: `db` | `wordpress` | `wordpress` |

## 🐞 Debugging with Xdebug

Xdebug is pre-configured and ready to use.

1.  Click the **Run and Debug** icon in the VS Code sidebar (Play icon with a bug).
2.  Select **"Listen for Xdebug"** from the dropdown.
3.  Click the green **Play button**.
4.  Add a breakpoint (click the red dot gutter) in your PHP code.
5.  Refresh your browser. VS Code will pause execution at your breakpoint.

## 🧰 Included Tools

* **WP-CLI:** Pre-installed. Run `wp` commands directly in the VS Code terminal.
* **Composer:** Not included by default but available via the terminal if needed.
* **Extensions:**
    * `PHP Intelephense` (Intellisense)
    * `PHP Debug` (Xdebug adapter)
    * `WordPress Toolbox` (Snippets and autocomplete)
    * `Prettier` (Formatter)

## 📂 Architecture

* **Source Code:** Your local folder is mounted to `/var/www/html/wp-content/plugins/local-dev-plugin`.
* **Database:** Persists in a Docker volume `db_data` (data survives container restarts).
* **Logs:** Xdebug logs are located at `/tmp/xdebug.log`.
