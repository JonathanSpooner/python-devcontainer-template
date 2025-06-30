# Python Dev Container Template

This repository provides a streamlined way to kickstart new Python projects with a consistent development environment using VS Code Dev Containers and `pyscaffold`.

## How to Use This Template

1.  **Clone the Repository:**
    Navigate to your desired projects directory on your remote server (via SSH) and clone this repository.
    ```bash
    cd ~/projects/
    git clone https://github.com/your-username/python-devcontainer-template.git my-new-project
    cd my-new-project
    ```
    *(Replace `your-username` with your GitHub username and `my-new-project` with your desired project name.)*

2.  **Open in VS Code:**
    Open the `my-new-project` folder in VS Code using the Remote - SSH extension.

3.  **Reopen in Container:**
    VS Code will detect the `.devcontainer` folder and prompt you to "Reopen in Container". Click this button.

    *What happens next:*
    *   VS Code will build the Docker image (if it's the first time) and start the container.
    *   Once the container is ready, a `postCreateCommand` will automatically run:
        *   `pip install pyscaffold`
        *   `putup .` (This will generate the standard `pyscaffold` project structure directly in your `my-new-project` folder.)

4.  **Start Coding!**
    Your new Python project, complete with a `pyscaffold` structure and a ready-to-use development environment, is now set up.

## Customizing `pyscaffold`

If you need to customize `pyscaffold` options (e.g., add specific extensions, choose a license), you can modify the `putup .` command in `.devcontainer/devcontainer.json` or run `putup` manually after the container starts.

For example, to add the `dsproject` extension:
```json
"postCreateCommand": "pip install pyscaffold && putup . --dsproject"
```
Refer to the [pyscaffold documentation](https://pyscaffold.org/en/latest/commands.html) for more options.
