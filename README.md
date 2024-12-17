# Toggle Hosts Script

**Toggle Hosts** is a simple command-line tool that automates switching between **localhost** and **remote IP** entries in your `/etc/hosts` file. It eliminates the need for manual editing and makes environment switching seamless.

---

## 📋 Features

- **Quick Environment Switching**: Easily toggle between `localhost` (127.0.0.1) and `remote IP` for specific domains.

- **Current Environment Detection**: Run without arguments to see whether you’re in **local** or **remote** mode.

- **Automated Sudo Privileges**: If you forget to run the script with `sudo`, it will prompt for the password and rerun itself.

---

## ⚙️ Installation

1. **Download the script**:

   ```bash
   $ curl -o ~/bin/toggle_hosts https://raw.githubusercontent.com/ulasarican/toggle-hosts/main/toggle-hosts
   ```

2.	**Make it executable**:
    ```bash
    $ chmod +x ~/bin/toggle_hosts
    ```

3.	**Add the script to your PATH (if ~/bin is not already in your PATH)**:
    
    •	For zsh users:
    ```bash
    $ echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc
    $ source ~/.zshrc
    ```
    •	For bash users:
    ```bash
    $ echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
    $ source ~/.bashrc
    ```

## 🚀 How to Use

1. **Show Current Environment**

    To check which environment is active (local or remote):

    ```bash
    $ toggle_hosts
    ```

    Output Example:
    ```bash
    $ Current Environment: LOCAL (localhost is active).
    ```

2. **Switch to local**

    Activate the localhost entries in the /etc/hosts file:

    ```bash
    $ toggle_hosts local
    ```

    Output
    ```bash
    Switched to LOCAL mode (localhost is active).
    Hosts file updated successfully.
    ```
    
3. **Switch to remote**

    Activate the remote entries in the /etc/hosts file:

    ```bash
    $ toggle_hosts remote
    ```

    Output
    ```bash
    Switched to REMOTE mode (remote IP is active).
    Hosts file updated successfully.
    ```

## 🛡️ Safety and Permissions
• The script requires root privileges to edit the /etc/hosts file.

• If you forget to run it with sudo, the script will automatically re-run itself and prompt for your password.

## 🛠️ Customization

You can modify the script to fit your domain names or IP addresses. Simply replace the following lines in the script:

```bash
LOCAL_LINE="127.0.0.1 your-domain.com"
REMOTE_LINE="x.x.x.x your-domain.com"
```

## 🤝 Contributions

Contributions are welcome! If you find a bug, need additional features, or want to improve the script, feel free to submit a pull request.

1.	Fork this repository.

2.	Create a branch (feature/my-feature).

3.	Commit your changes.

4.	Submit a pull request.

## 💬 Feedback

If you have any feedback, suggestions, or issues, please open an issue in this repository.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.