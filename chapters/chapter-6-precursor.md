# Precursor: Login and Accessing with Postman

## Overview

Using Adobe AdminConsole to manage an Experience Platform instance, manage Product Profiles, manage users and administrators. Validate if login to Experience Platform UI succeeds.

## Learning Objectives

- Understand AdminConsole capabilities for Experience Platform
- Understand the role of Product Profiles
- Access control through service -settings
- Managing users and administrators

## Lab Resources

- AdminConsole: [https://adminconsole.adobe.com/](https://adminconsole.adobe.com/)
- Experience Platform UI: [https://platform.adobe.com/](https://platform.adobe.com/)

## Lab Tasks

- Log into Adobe Cloud Platform
  - Create Product Profile
  - Add Users
  - Add as Admin
- Setup an integration
- Authenticate via POSTMan

### Login to Admin Console

1. Navigate to [https://adminconsole.adobe.com](https://adminconsole.adobe.com) in your browser
1. Login with the “master credentials for lab” that are provided on your personal lab-worksheet.

   ![](/images/chapter-2/adminlogin.png)

1) Select “Adobe Cloud Platform – Data Services”

   ![](/images/chapter-2/data_services.png)

1) Select “New Profile”

   ![](/images/chapter-2/new_profile.png)

1) Complete your Product Profile details (for prefix see your Lab worksheet):
   - Profile Name : Profile-<prefix>
   - Display Name : [V] Same as Profile Name
   - Description: Product Profile for <prefix>
   - Disable User notifications
1) Click “Next”

   ![](/images/chapter-2/next.png)

1) Select the Services you want to enable for this Product Profile
   - Enable “Data Science Workspace”
   - Enable “Experience Query Service”
1) Select “Done”

   ![](/images/chapter-2/done.png)

1) Click on the Product Profile you just created

   ![](/images/chapter-2/product_profile.png)

1) Click “Add User”

   ![](/images/chapter-2/add_user.png)

1) Type your own Personal AdobeId (see Lab Worksheet)

   ![](/images/chapter-2/personal_adobe_id.png)

1) Your user has been added to the Product Profile – you can now login into Experience Platform, but just one more thing…….
1) Go back to “Overview”

   ![](/images/chapter-2/adminlogin.png)

1) Click “Add Admin”, Add your AdobeId (see Lab Worksheet) and enable “System Administrator” privileges.
   N.B. This is only needed if the user needs to create Integrations using I/O Console
1) Go to [https://platform.adobe.com/](https://platform.adobe.com/)

### Setup an integration

1. Create Certificate

   **For MacOS & Linux platform**

   Open terminal and execute below command:

   ```shell
   openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
   ```

   **For Windows Platform**

   Open Command Line Prompt and execute below commands.

   ```shell
   set OPENSSL_CONF=C:/libs/openssl-1.1.1-win64-mingw/openssl.cnf
   cd C:/libs/openssl-1.1.1-win64-mingw/
   openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
   ```

   You will get a response similar to the following which prompts you to enter some information about yourself:

   ```
   Generating a 2048 bit RSA private key
   .................+++
   .......................................+++
   writing new private key to 'private.key'
   -----
   You are about to be asked to enter information that will be incorporated
   into your certificate request.
   What you are about to enter is what is called a Distinguished Name or a DN.
   There are quite a few fields but you can leave some blank
   For some fields there will be a default value,
   If you enter '.', the field will be left blank.
   -----
   Country Name (2 letter code) []:
   State or Province Name (full name) []:
   Locality Name (eg, city) []:
   Organization Name (eg, company) []:
   Organizational Unit Name (eg, section) []:
   Common Name (eg, fully qualified host name) []:
   Email Address []:
   ```

   After entering the information two files will be generated: `certificate_pub.crt` and `private.key`. These files can be found in the same directory that you ran the `openssl` command from.

   Note `certificate_pub.crt` will expire in 365 days. You can make the period longer by changing the value of days in the openssl command above but rotating credentials periodically is a good security practice.

   The `certificate_pub.crt` certificate will later be uploaded to the Adobe IO Console for when you create an API key for access to any Adobe I/O API.

   Your private key file named `private.key` will be used later to sign your JWT token.

   > Note: Don't close this terminal window as you will need it later.

1. Navigate to the [Adobe I/O Console](https://console.adobe.io/) and sign in with your Adobe ID.
1. From this page we want to create a New Integration.

   ![](/images/chapter-2/new_integration.png)

1. You will then be prompted to Access an API or to Receive near-real-time events. We will be accessing APIs so select Access an API and then Continue.

   ![](/images/chapter-2/new_integration1.png)

1. The drop-down menu on the top right of the screen is where you would switch your organization if your account is tied to multiple. We are selecting **Workshop** and Data Services under Experience Cloud since we want to access the data services.

   ![](/images/chapter-2/new_integration2.png)

1. After your organization is selected there will be a new prompt at the top. We want a New Integration so make sure that option is selected before clicking Continue

   ![](/images/chapter-2/new_integration3.png)

1. Fill in your Integration Details. Afterwards, click on Select a File to upload your certificate_pub.crt file we generated in the previous section. Click Create Integration to finish up the process

   ![](/images/chapter-2/new_integration4.png)

1. After creating your integration, you will be able to view the details of your integration. After clicking on Retrieve client Secret your screen should look similar to this.

   ![](/images/chapter-2/access_values.png)

   Copy down the values for {API KEY}, {IMS ORG} which is the Organization ID, and {CLIENT SECRET} as these will be used in the next step.

### Authenticate via POSTMan

1. Start POSTMan

   ![](/images/chapter-2/postman.png)

1. Click the `Import` button on the top left.

   ![](/images/chapter-2/postman_import.png)

   Select the [ExperiencePlatform.postman_collection.json](postman/ExperiencePlatform.postman_collection.json) collection file from this repository.

1. Next we need to import our environment. Click on the settings logo

   ![](/images/chapter-2/postman_settings.png)

   To bring up the **Manage Environments** dialog.

   ![](/images/chapter-2/postman_manage_env.png)

1. Then click on `Import`

   ![](/images/chapter-2/postman_import_env.png)

1. Select the [ExperiencePlatform.postman_environment.json](postman/ExperiencePlatform.postman_environment.json) file to import the environment.

   ![](/images/chapter-2/postman_after_env_import.png)

1. Now click on the newly imported `Adobe Experience Platform - Environment`.

   ![](/images/chapter-2/postman_set_env.png)

1. Fill out the values for:

   - clientID
   - clientSecret
   - OrgID
   - TechAcctID

   that you generated when you created your **new integration**.

   Also fill out the `ldap` field with your user id so you'll be able to uniquely identify the datasets you create.

1. Copy the contents of the `private.key` and use it as the value for `secret`.

   **For MacOS & Linux platform**

   From the same terminal you ran `openssl`, execute the following command:

   ```shell
   pbcopy < private.key
   ```

   **For Windows Platform**

   From the same terminal you ran `openssl`, execute the following command:

   ```shell
   notepad private.key
   ```

   Copy the entire key to the keyboard, including the `-----BEGIN PRIVATE KEY-----` and `-----END PRIVATE KEY-----` lines.

1. Click `Update` and close the `Manage Environments` dialog.

1. Now make sure you select the `Adobe Experience Platform - Environment` from the environments drop down at the top right of POSTMan.

   ![](/images/chapter-2/postman_experience_platform_env.png)

1. After all this setup you are now ready to generate an JWT and bearer token to interact with Adobe I/O. In order to make this process easier we'll be using an Adobe I/O Runtime action.

   From our newly imported `Adobe Experience Platform` collection, open chapter 2 and click on `Adobe I/O Runtime: Generate Auth`. Then click on the body tab:

   ![](/images/chapter-2/postman_auth_body.png)

   All of that work you did to setup the environment has been put to good use. Each POSTMan call will take advantage of these values.

1. Now click `Send` and scroll down to the response section:

   ![](/images/chapter-2/postman_auth_response.png)

   That JSON response includes an `access_token` which is the Bearer token used to authenticate with Adobe I/O. The POSTMan call will save this value in an environment variable for future use.

Whew! We are finally ready to start calling the Adobe Experience Platform API's for real.

---

### Navigate

**Previous:** Chapter 5 - [UI: Segment the Data](chapter-1.md)
**Next:** Chapter 6 - [API: Define the Schema](chapter-3.md)
