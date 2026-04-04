# OpenClaw Installation Guide for macOS

## Prerequisites

### Install and Update Homebrew

Before getting started, make sure Homebrew is installed on your system and packages are up to date:

1. Visit the [official Homebrew website](https://brew.sh) and copy the installation command shown on the page.

    ![image.png](../assets/image%2029.png)

2. Paste the command into your terminal window. Press **Enter** to confirm that you want to install Homebrew and wait for the installation to complete.

3. Update the package list by running:

    ```bash
    brew update
    ```

    ![image.png](../assets/image%2030.png)


### Install Node.js and NPM on Mac

After installing Homebrew, follow the steps below to install Node.js and NPM:

1. Run the install command:

    ```bash
    brew install node
    ```

    Homebrew will download and install Node.js, NPM packages, and their dependencies.

    ![image.png](../assets/image%2031.png)

2. Confirm that Node.js was installed successfully by checking the version:

    ```bash
    node -v
    ```

    The system will display the installed Node.js version.

     ![image.png](../assets/image%2032.png)

3. Check the installed NPM version by running:

    ```bash
    npm -v
    ```

    The NPM version number will be displayed.

     ![image.png](../assets/image%2033.png)


## Install and Set Up OpenClaw

### Installation

Open **Terminal** and run the following command:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

After entering the command, wait for the installation to complete — this usually takes a few minutes.

![image.png](../assets/image%2034.png)


### Initial Setup

#### Controls

- Use arrow keys (**←**/**→**) to move left/right
- Use arrow keys (**↑**/**↓**) to move up/down
- Press `Space` to select options marked with **☐**
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

**Note:** After step 10, OpenClaw will automatically open a new terminal window to run the gateway. If it doesn't open automatically, you can start it manually:

```bash
openclaw gateway
```

![image.png](../assets/image%2017.png)

Keep the gateway running at all times to use OpenClaw and allow OpenClaw to operate on macOS.

### Using the Dashboard

Open **Terminal** and run the following command:

```bash
openclaw dashboard
```

The dashboard will open automatically in your browser.

![image.png](../assets/image%2018.png)

If it doesn't open automatically, copy the URL and open it in your browser.


### Using a Chat Channel

There are multiple channels available. This guide uses Telegram.

#### Set Up a Telegram Chat Channel

Open **Terminal** and run the following command (instructions for getting the bot token are below).

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

Open **Terminal** and run the following command (instructions for getting the code are below):

```bash
openclaw pairing approve telegram <code>
```

![image.png](../assets/image%2035.png)

#### How to Get the Pairing Code

1. Open Telegram, search for the username of the bot you just created, and press Start.

    ![image.png](../assets/image%2027.png)

2. Copy the code shown in the chat and use it in the command above.

    ![image.png](../assets/image%2028.png)


## Summary

This guide has walked you through the complete installation and setup of OpenClaw, with Telegram as the chat channel.
