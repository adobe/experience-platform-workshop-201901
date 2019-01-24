# Chapter 1. Setup: Before you start -  Pre-Authorization

## Check access to Adobe Solutions

- Go to [Adobe Admin Console](https://adminconsole.adobe.com) and make sure you have access to the workshop org
  - Refer to [Admin Console helpx page](https://helpx.adobe.com/enterprise/using/admin-console.html) if you run into issues accessing your org.
- In your organization, make sure you have access to the following Adobe Solutions
  - Adobe Experience Platform

---

## Check access to Adobe I/O Console

- Go to [Adobe I/O Console](https://console.adobe.io/), step through the beginning few steps of creating a new integration till you get to a list of APIs.
  - If you have administrative privileges for your organization and you are authorized for Adobe Solutions, you should see them listed and not grayed out on this screen.
  - If you do not have the required permissions, contact an instructor for help.

---

## Set up your local

### Download

Download the resources listed on top and make sure they are accessible on your local.

#### Required tools

In this workshop you would need the following items set on on your local:

- [Postman](https://www.getpostman.com/apps)

For Windows users, please make sure you have **OpenSSL** set up

- Download an OpenSSL client [OpenSSL](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip)
- Extract the folder and copy it to the `C:/libs/` location.
- Open a command prompt and run the following commands:
```shell
set OPENSSL_CONF=C:/libs/openssl-1.1.1-win64-mingw/openssl.cnf
cd C:/libs/openssl-1.1.1-win64-mingw/
```
- Leave this command prompt open as you will need it later.

Mac users will be able to use the default version of **OpenSSL** included with MacOS.

#### Recommended tools

---

### Navigate

**Next:** Chapter 2 - [XDM and Experience Platform Overview](chapter-2.md)
