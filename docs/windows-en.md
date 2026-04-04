# OpenClaw Installation Guide for Windows

## Prerequisites

### Install Winget (Windows Package Manager)

Winget (Windows Package Manager) is usually pre-installed on Windows 11 and recent versions of Windows 10.

1. Open **Command Prompt**, type `winget -v`. If a version number is shown, you already have winget.

    ![image.png](../assets/image%200.png)

2. If you don't have it, open the Microsoft Store, search for **"App Installer"**, and click "Update" or "Install".

    ![image.png](../assets/image%201.png)


### Install Node.js

1. Open **Command Prompt** as Administrator (right-click → Run as administrator).
2. Run the following command:

    ```bash
    winget install -e --id OpenJS.NodeJS
    ```

    ![image.png](../assets/image%202.png)

3. If prompted with licence agreements, type `Y` or press Enter to agree and continue.
4. After installation, close and reopen **Command Prompt**, then verify the installation:

    ```bash
    node -v
    npm -v
    ```

    ![image.png](../assets/image%203.png)


## Install and Set Up OpenClaw

### Installation

1. Open **Command Prompt** and run the following command:

    ```bash
    npm install -g openclaw@latest
    ```

    ![image.png](../assets/image%204.png)

2. Open **Command Prompt** and type `openclaw -v`. If a version number is shown, OpenClaw is installed.

    ![image.png](../assets/image%205.png)


### Initial Setup

#### Controls

- Use arrow keys (**←**/**→**) to move left/right
- Use arrow keys (**↑**/**↓**) to move up/down
- Press `Space` to select options marked with **⃞**
- Press `Enter` to confirm a selection

#### Run Setup

```bash
openclaw onboard --install-daemon
```

1. **I understand this is personal-by-default and shared/multi-user use requires lock-down. Continue?**

    Select `Yes`

    ![image.png](../assets/image%206.png)

2. **Setup mode**

    Select `QuickStart`

    ![image.png](../assets/image%207.png)

3. **Model/auth provider**

    Select `Google`

    ![image.png](../assets/image%208.png)

4. **Enter Gemini API key**

    Enter your API key (get one from [Google AI Studio](https://aistudio.google.com/api-keys))

    ![image.png](../assets/image%209.png)

5. **Default model**

    Select `google/gemini-2.5-flash`

    ![image.png](../assets/image%2010.png)

6. **Select channel (QuickStart)**

    Select `Skip for now`

    ![image.png](../assets/image%2011.png)

7. **Search provider**

    Select `Skip for now`

    ![image.png](../assets/image%2012.png)

8. **Configure skills now? (Recommended)**

    Select `No`

    ![image.png](../assets/image%2013.png)

9. **Enable hooks?**

    Select `Skip for now`

    ![image.png](../assets/image%2014.png)

10. **How do you want to hatch your bot?**

    Select `Do this later`

    ![image.png](../assets/image%2015.png)


Once all selections are made, the initial setup is complete.

![image.png](../assets/image%2016.png)

**Note:** After step 9, OpenClaw will automatically open a new terminal window to run the gateway. If it doesn't open automatically, you can start it manually:

```bash
openclaw gateway
```

![image.png](../assets/image%2017.png)

Keep the gateway running at all times to use OpenClaw and allow OpenClaw to operate on Windows.

### Using the Dashboard

Open **Command Prompt** and run the following command:

```bash
openclaw dashboard
```

The dashboard will open automatically in your browser.

![image.png](../assets/image%2018.png)

If it doesn't open automatically, copy the URL and open it in your browser.

![image.png](../assets/image%2019.png)

### Using a Chat Channel

There are multiple channels available. This guide uses Telegram.

#### Set Up a Telegram Chat Channel

Open **Command Prompt** and run the following command (instructions for getting the bot token are below).

```bash
openclaw channels add --channel telegram --token <bot-token>
```

![image.png](../assets/image%2020.png)

#### How to Get a Bot Token

1. Open Telegram, search for BotFather, and press Start.

    ![image.png](../assets/image%2021.png)

2. Type `/newbot` in the chat and press `Enter`.

    ![image.png](../assets/image%2022.png)

3. Enter a name for your bot.

    ![image.png](../assets/image%2023.png)

4. Choose a username for your bot — it must end with `bot`.

    ![image.png](../assets/image%2024.png)

5. The bot token will appear in the chat. Copy it and use it in the command above.

    ![image.png](../assets/image%2025.png)


#### How to Pair OpenClaw with Your Telegram Bot

To allow the Telegram bot to interact on behalf of OpenClaw, you need to pair them.

Open **Command Prompt** and run the following command (instructions for getting the code are below):

```bash
openclaw pairing approve telegram <code>
```

![image.png](../assets/image%2026.png)

#### How to Get the Pairing Code

1. Open Telegram, search for the username of the bot you just created, and press Start.

    ![image.png](../assets/image%2027.png)

2. Copy the code shown in the chat and use it in the command above.

    ![image.png](../assets/image%2028.png)


## Summary

This guide has walked you through the complete installation and setup of OpenClaw, with Telegram as the chat channel.
