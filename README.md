# Git/GitHub Bootcamp 2024
Repository for demonstrating git and GitHub functionality for UIdaho CS bootcamp on 9/25/2024

## Git Installation and Setup Guide

### **1. Installing Git**

#### **Windows**
1. **Download Git**:  
   Go to [git-scm.com](https://git-scm.com/download/win) and download the Git installer for Windows.
   
2. **Run the Installer**:  
   Run the `.exe` file you downloaded and follow the installation steps:
   - Use the default settings unless you need specific configurations.
   - Select **"Use Git from the Windows Command Prompt"** when prompted.
   
3. **Verify Installation**:  
   After installation, open **Git Bash** (installed with Git) or the Command Prompt and run the following command to verify:
   ```bash
   git --version
   ```

#### **macOS**
1. **Install via Homebrew (Recommended)**:  
   If you have [Homebrew](https://brew.sh/) installed, open the Terminal and run:
   ```bash
   brew install git
   ```

2. **Install via Xcode Command Line Tools**:  
   Alternatively, you can install Git by running this in Terminal:
   ```bash
   xcode-select --install
   ```

3. **Verify Installation**:  
   Once installed, verify the installation by running:
   ```bash
   git --version
   ```

#### **Linux**
1. **Ubuntu/Debian**:  
   Open a terminal and run:
   ```bash
   sudo apt update
   sudo apt install git
   ```

2. **Fedora**:  
   Open a terminal and run:
   ```bash
   sudo dnf install git
   ```

3. **Arch Linux**:  
   Open a terminal and run:
   ```bash
   sudo pacman -S git
   ```

4. **Verify Installation**:  
   Verify Git is installed by running:
   ```bash
   git --version
   ```

---

### **2. Creating a GitHub Account**

1. **Go to GitHub**:  
   Visit [github.com](https://github.com/) and click **Sign up** in the upper-right corner.

2. **Sign Up**:  
   Follow the steps to create a GitHub account by providing your email address, creating a username and password, and following the verification process.

3. **Verify Email**:  
   Check your inbox for a verification email from GitHub. Click the verification link to complete the sign-up process.

4. **Configure Your Profile** (Optional):  
   You can set up your GitHub profile with a bio, profile picture, and other details from your GitHub dashboard.

---

### **3. Setting Up an SSH Key for GitHub**

#### **Windows**
1. **Open Git Bash**:  
   Launch **Git Bash** from the Start Menu.

2. **Generate an SSH Key**:  
   Run the following command, replacing `your_email@example.com` with the email address associated with your GitHub account:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   - If your system does not support `ed25519`, use `rsa` with the following command:
     ```bash
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ```

3. **Save the Key**:  
   When prompted to "Enter a file in which to save the key," press **Enter** to accept the default location (`~/.ssh/id_ed25519`).

4. **Set a Passphrase** (Optional):  
   You can set a passphrase for added security. Press **Enter** to skip if you don’t want one.

5. **Add the SSH Key to the SSH Agent**:  
   Run the following commands to start the SSH agent and add your key:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

6. **Copy the SSH Key**:  
   Copy the key to your clipboard by running:
   ```bash
   clip < ~/.ssh/id_ed25519.pub
   ```
   - Alternatively, open the file manually and copy the contents.

7. **Add SSH Key to GitHub**:  
   - Go to [GitHub SSH Keys Settings](https://github.com/settings/keys).
   - Click **New SSH key**.
   - Paste the copied key into the **Key** field, add a **Title** (e.g., "My Laptop"), and click **Add SSH key**.

8. **Test SSH Connection**:  
   Run the following command to test the connection:
   ```bash
   ssh -T git@github.com
   ```
   If successful, you'll see a message like:
   ```
   Hi username! You've successfully authenticated, but GitHub does not provide shell access.
   ```

#### **macOS**
1. **Open Terminal**:  
   Use Spotlight (Cmd + Space) and search for **Terminal**.

2. **Generate an SSH Key**:  
   Run the following command, replacing `your_email@example.com` with your GitHub email:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

3. **Save the Key**:  
   Press **Enter** to save the key to the default location (`/Users/your_user/.ssh/id_ed25519`).

4. **Add the SSH Key to the SSH Agent**:  
   Run these commands to start the SSH agent and add your SSH key:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

5. **Copy the SSH Key**:  
   Run the following command to copy the key:
   ```bash
   pbcopy < ~/.ssh/id_ed25519.pub
   ```

6. **Add SSH Key to GitHub**:  
   - Go to [GitHub SSH Keys Settings](https://github.com/settings/keys).
   - Click **New SSH key** and paste the key.

7. **Test SSH Connection**:  
   Test the connection with:
   ```bash
   ssh -T git@github.com
   ```

#### **Linux**
1. **Open Terminal**:  
   Launch the Terminal from your application menu.

2. **Generate an SSH Key**:  
   Run this command (replace `your_email@example.com` with your GitHub email):
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

3. **Save the Key**:  
   Press **Enter** to save the key in the default location (`~/.ssh/id_ed25519`).

4. **Start the SSH Agent and Add Your Key**:  
   Run these commands:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

5. **Copy the SSH Key**:  
   Use this command to copy the SSH key:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   Then manually copy the output.

6. **Add SSH Key to GitHub**:  
   - Go to [GitHub SSH Keys Settings](https://github.com/settings/keys).
   - Click **New SSH key** and paste the copied key.

7. **Test SSH Connection**:  
   Test the connection with:
   ```bash
   ssh -T git@github.com
   ```
