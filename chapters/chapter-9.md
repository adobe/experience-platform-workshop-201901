# Chapter 9. Technical: Stream in Data via Launch

## Learning Objectives

- Learn how to integrate Adobe Experience Platform Launch onto a webpage
- Create Launch rules to stream data to Experience Platform

## Lab Resources

- Launch URL:

## Lab Tasks

- Deploy webpage on local server
- Create Launch property and add streaming endpoint to webpage
- Create data element and rule to stream a data beacon into Experience Platform
- Observe the beacon firing, and landing in Experience Platform

---

## Story

---

## Steps

### Deploying webpage to your machine

1.  Download the [WeTravel website](../data/WeTravel-local.zip).
1.  Unzip the `WeTravel-local.zip` file and make note of which directory you extract the content to.
1.  Start the Fenix web server.

    ![](../images/chapter-9/start-fenix.png)

1.  Select the `Web Servers` menu and click `New`

    ![](../images/chapter-9/new-server.png)

1.  Use `WeTravel` as descriptive name.

    ![](../images/chapter-9/we-travel.png)

1.  Click on the folder in the `Directory` input field. Then navigate the file dialog to the directory you unzipped the `WeTravel-local` folder, highlight it and click `Select`.

    ![](../images/chapter-9/select-folder.png)

1.  Click `Create`.

    ![](../images/chapter-9/create.png)

1.  Click on the `Play` button to start the server.

    ![](../images/chapter-9/click-start.png)

1.  Now your WeTravel site should be ready to be browsed.

    ![](../images/chapter-9/server-started.png)

1.  Navigate to [http://127.0.0.1](http://127.0.0.1) to test the web server. You should see the following:

    ![](../images/chapter-9/localhost.png)

1.  Now we need to redirect requests to `we-travel.com` to our local web server.

    For **MacOS** users:

    - Open the Terminal program.
    - Run the following command:

              sudo nano /etc/hosts

      - You will need to type in your adminstrator password to continue.

      ![](../images/chapter-9/sudo-nano.png)

      - You're now in the Nano text editor. You should see something that looks like this:
      - Use the arrow keys to navigate the cursor to the line:

              127.0.0.1  localhost

      ![](../images/chapter-9/localhost-line.png)

      - Add `we-travel.com` to the end of the line so it looks like:

              127.0.0.1  localhost   we-travel.com

      ![](../images/chapter-9/we-travel-line.png)

      - Once you're done, hold down the control and O keys to save the file, then control and X to exit.
      - Finally you'll need to restart your Mac's DNS responder by entering the following command into the Terminal:

              sudo killall -HUP mDNSResponder

    For **Windows** users:

    - Press the Windows key.
    - Type **Code** in the search field.
    - In the search results, right-click **Code** and select **Run as administrator**.
      From **Code**, open the following file:

            c:\Windows\System32\Drivers\etc\hosts

    - Add a new line to the end of the file that looks like this:

            127.0.0.1   we-travel.com

    - Click File > Save to save your changes.

1.  Navigate to [http://we-travel.com](http://we-travel.com) to test the web server. You should see the following:

    ![](../images/chapter-9/not-localhost.png)

### Setting up Adobe Launch

### Streaming a Launch data beacon into Platform

---

### Navigate

**Previous:** Chapter 8 - [Technical: Query the Data](chapter-8.md)
