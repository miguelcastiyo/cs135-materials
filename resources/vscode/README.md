# Setting Up Visual Studio Code (VSCode) for Remote C++ Development

> **Note**: These instructions are for Visual Studio Code (often abbreviated as VSCode), a lightweight, cross-platform code editor. This is different from Visual Studio, a separate, full-featured integrated development environment (IDE) primarily for Windows. Be sure to download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com/) to follow these steps.

### Note on Initial VSCode Setup

- When you first open VSCode, you may be prompted to go through some initial setup steps, like selecting a theme or configuring settings.
- **For now, it’s best to skip these steps** to avoid unnecessary setup and go directly to installing the required extensions and setting up the server connection.
- You can return to these options anytime by going to **File > Preferences** on Windows or **Code > Settings** on macOS if you want to personalize your environment later.

---

### Part 1: Download and Install Visual Studio Code

#### For Windows Users
1. **Download VSCode**:
   - Go to [https://code.visualstudio.com/](https://code.visualstudio.com/) in your web browser.
   - Click the **Download for Windows** button and save the file.

2. **Install VSCode**:
   - Open your **Downloads** folder and double-click the downloaded `.exe` file.
   - When prompted, click **Run** to start the installation.
   - Follow the installation steps:
     - **Accept the license agreement** by checking the box and clicking **Next**.
     - Choose an installation location (the default is fine).
     - **Select the options** to:
       - Add **VSCode to PATH** (recommended for easy command-line access).
       - Optionally, choose **Create a desktop shortcut** for quick access.
   - Click **Install**. Once complete, click **Finish** to open VSCode for the first time.

#### For macOS Users
1. **Download VSCode**:
   - Go to [https://code.visualstudio.com/](https://code.visualstudio.com/) in your web browser.
   - Click the **Download for macOS** button.

2. **Install VSCode**:
   - Open your **Downloads** folder and double-click the downloaded `.zip` file. This will automatically extract a new **Visual Studio Code** application.
   - Drag the **Visual Studio Code** application into your **Applications** folder.
   - To open VSCode, go to **Applications** and double-click on **Visual Studio Code**.

---

### Part 2: Install the Required Extensions

1. **Open the Extensions Panel**:
   - In VSCode, click the **Extensions** icon on the left sidebar (it looks like four squares).

2. **Install Remote - SSH (by Microsoft)**:
   - In the Extensions search bar, type **Remote - SSH**.
   - Click on **Remote - SSH** in the search results, then click **Install**.

3. **Install C/C++ (by Microsoft)**:
   - In the Extensions search bar, type **C/C++**.
   - Be sure to select the **C/C++ Extension** by Microsoft, **not** the **C/C++ Extension Pack**. The **C/C++ Extension** provides essential features like IntelliSense, debugging, and code navigation without additional components that could use up space.
   - Click **Install**.

---

### Part 3: Add the Server as a New SSH Host (First Connection Only)

1. **Prepare Your Server Details**:
   - The server address is `bellagio.csn.edu`, using the default SSH port (22).
   - Your username format is the letter 'a' followed by your ten-digit NSHE student ID number. For example, if your NSHE number is `1234567890`, your username is `a1234567890`.
   - Have your password ready, as you’ll be asked for it during connection.

2. **Open the Command Palette in VSCode**:
   - On **Windows**: Press `Ctrl + Shift + P` or `F1`.
   - On **macOS**: Press `Cmd + Shift + P` or `Fn + F1`.

3. **Add the Server as a New SSH Host**:
   - In the Command Palette, start typing **Remote-SSH: Add** until the option appears, then select **Remote-SSH: Add new SSH Host…** from the list.
   - When prompted, enter the following SSH connection string, using the username format from Step 1:
     ```bash
     ssh <username>@bellagio.csn.edu
     ```
     - **Example**: If your username (from Step 1) is `a1234567890`, enter `ssh a1234567890@bellagio.csn.edu`.
   - Press **Enter**.

4. **Select the Configuration File and Verify**:
   - You may be prompted to select an SSH configuration file location. Choose the default option provided:
     - **Windows**: `C:\Users\YourName\.ssh\config`
     - **macOS**: `/Users/YourName/.ssh/config`
   - After selection, your configuration file should contain an entry like this:
     - **For macOS and Linux users**:
       ```plaintext
       Host bellagio.csn.edu
         HostName bellagio.csn.edu
         User a1234567890
       ```
     - **For Windows users**:
       ```plaintext
       Host bellagio.csn.edu
         HostName bellagio.csn.edu
         User a1234567890
         MACs hmac-sha2-256
       ```
       The additional `MACs` line is required on Windows due to the SSH server configuration.
   - Be sure to replace `a1234567890` with your actual username, then save the file.


---

### Part 4: Connect to the Server Remotely

1. **Connect to the Server**:
   - Open the **Command Palette** again, type **Remote-SSH: Connect to Host**, and select `bellagio.csn.edu` from the list of hosts.

2. **Confirm the Server’s Identity**:
   - The first time you connect, you may see a prompt asking if you trust this server. Type **yes** and press **Enter** to continue.
   - Enter your **password** when prompted (note: you won’t see the characters appear as you type).
   - Upon successful login, you will be placed in your **home directory** on the server (e.g., `/home/a1234567890`).

3. **Set the Remote Platform**:
   - If prompted to select the platform type, choose **Linux**.

4. **Open Your Project Directory in Explorer**:
   - Click on the **Explorer** icon on the left sidebar.
   - Select **Open Folder**. The directory listing will start in your **home directory**.
   - Navigate to the directory you created for your project (e.g., `cs135`) and select it.
   - This allows you to work directly in your project folder on the server.

5. **Trust the Folder**:
   - When opening your project folder, VSCode will present a dialog asking, "Do you trust the authors of the files in this folder?"
   - Since you are working with your own files, select **Yes, I trust the authors** to proceed.

6. **Wait for the Connection to Complete**:
    - After a moment, you should see a new VSCode window connected to `bellagio.csn.edu`. You are now working on the server.

---

### Part 5: Open the Terminal in VSCode

- **Open a Terminal Window**:
   - In the top VSCode menu, go to **Terminal > New Terminal**.
   - Alternatively, you can quickly open a terminal with the shortcut **Ctrl + `** (Ctrl plus backtick).
   - This opens a command-line terminal connected to `bellagio.csn.edu`, where you can navigate directories, compile code, and perform other tasks.

---

### Part 6: Set Up and Test C++ Development Environment

1. **Navigate to or Create a Directory for Your Work**:
   - In the terminal, you can navigate to an existing folder or create a new one with these commands:
     ```bash
     mkdir -p ~/cs202/project   # creates a new directory named 'project'
     cd ~/cs202/project/        # moves into the new directory
     ```

2. **Create a New C++ File in VSCode**:
   - In the **Explorer** view, right-click inside your project folder and select **New File**.
   - Name the file `hello.cpp` and press Enter.
   - **Note**: VSCode may display a prompt asking, "Do you want to install the recommended 'C/C++ Extension Pack' extension from Microsoft for the C++ language?"
     - Since you already installed the necessary **C/C++ Extension** earlier, and to conserve space on your limited server quota, click on the **gear icon** in the prompt and select **Don't Show Again for this Extension**.
   - If prompted with an option to **ignore all future extension recommendations**, select this option as well. This will prevent further prompts for additional extensions, helping you stay within your storage quota.
   - Add a simple C++ program to test:
     ```cpp
     #include <iostream>
     int main() {
         std::cout << "Hello, World!" << std::endl;
         return 0;
     }
     ```

3. **Compile the Program**:
   - In the terminal, use the following command to compile the program:
     ```bash
     $ g++ $CXXFLAGS hello.cpp -o hello
     ```
   - If the command completes without error messages, an executable file named `hello` has been created.

4. **Run the Program**:
   - In the terminal, run the executable with:
     ```bash
     ./hello
     ```
   - You should see this output:
     ```
     Hello, World!
     ```

---

### Part 7: Logging Out and Reconnecting

1. **Close the Remote Connection**:
   - When finished, go to **File > Close Remote Connection** in VSCode.
   - Alternatively, you can simply close the VSCode window connected to the server to log out.

2. **Reconnect Anytime**:
   - To reconnect, simply follow the steps in **Part 4: Connect to the Server Remotely**.

---

### Optional: Using Code Runner for Quick Code Execution

1. **Install Code Runner on the Server**:
   - After connecting to the server as outlined in **Part 4**, go to the **Extensions** panel.
   - Search for **Code Runner** and open its information page.
   - Click **Install in SSH: bellagio.csn.edu** to install Code Runner on the server.
   - **Note**: This will consume part of your storage quota, so consider using the terminal instead if you prefer to conserve space.

2. **Run Code with Code Runner**:
   - Open your `.cpp` file (e.g., `hello.cpp`) in the editor.
   - Click the **play icon** (triangle pointing right) in the upper-right corner of the editor. Code Runner will compile and execute your code automatically.
   - **Note**: Code Runner does not use `$CXXFLAGS` by default, so use the terminal if specific flags are required.

