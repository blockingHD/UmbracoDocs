---
versionFrom: 9.0.0
meta.Title: "Security in Umbraco"
meta.Description: "This section includes information on Umbraco security, its various security options and configuring how authentication & authorization works in Umbraco"
---

# Security

In this article, you will find everything you need regarding security within Umbraco.

## [The Umbraco Trust Center](https://umbraco.com/about-us/trust-center/)

On our main website, we have a dedicated security section which provides all the details you need to know about security within the Umbraco CMS. This includes how to report a vulnerability.

## [SSL/HTTPS](use-https.md)

We highly encourage the use of HTTPS on Umbraco websites, especially in production environments. By using HTTPS you greatly improve the security of your website.

In the "Use HTTPS" article you can learn more about how to use HTTPS and how to set it up.

## [Password settings](Security-settings/index.md)

Learn which password settings that can be configured in Umbraco.

## [Security Hardening](Security-hardening/index.md)

Learn about how to can harden the security on your Umbraco website to secure it even further.

## [Security on Umbraco Cloud](../../Umbraco-Cloud/Frequently-Asked-Questions/#security-and-encryption)

When your project is hosted on Umbraco Cloud, you might be interested in more details about the security of the hosting. This information can be found in the Umbraco Cloud section of the documentation.

## Backoffice users

Authentication for backoffice users in Umbraco uses [ASP.NET Core Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity) which is a flexible and extendable framework for authentication.

Out of the box Umbraco ships with a custom ASP.NET Core Identity implementation which uses Umbraco's database data. Normally this is fine for most Umbraco developers, but in some cases the authentication process needs to be customized.

### [External login providers](external-login-providers/index.md)

The Umbraco backoffice supports external login providers (OAuth) for performing authentication of your users.
This could be any OpenIDConnect provider such as Azure Active Directory, Identity Server, Google or Facebook.

### [BackOfficeUserManager](backoffice-user-manager.md) and Notifications

The [`BackOfficeUserManager`](backoffice-user-manager.md) is the ASP.NET Core Identity [UserManager](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.identity.usermanager-1) implementation in Umbraco. It exposes APIs for working with Umbraco Users via the ASP.NET Core Identity including password handling.

### Custom password check

In most cases [External login providers (OAuth)](external-login-providers/index.md) will meet the needs of most users when needing to authenticate with external resources but in some cases you may need to only change how the username and password credentials are checked.

This is typically a legacy approach to validating credentials with external resources but it is possible.

You are able to check the username and password against your own credentials store by implementing a [`IBackOfficeUserPasswordChecker`](custom-password-checker.md).

## Sensitive data on members

Marking fields as **sensitive** will hide the data in those fields for backoffice users that do not have permission to view personal data of members.

Learn more about this in the [Sensitive Data](sensitive-data.md) article.

## [Setup Umbraco for a FIPS Compliant Server](Setup-Umbraco-for-a-Fips-Server/index.md)

How to configure Umbraco to run on a FIPS compliant server.

## [Reset admin password](reset-admin-password.md)

Use this guide to [reset the password of the "admin" user](reset-admin-password.md).

If you need to reset accounts of every other user while you still have administrative action, check this "[reset normal user password](password-reset.md)" article.

## Other articles related to security

* [Routing requirements for backoffice authentication](../Routing/Authorized/)
* [Health Checks](../../Extending/Health-Check/)
* [Consent Service](../Management/Services/ConsentService/)
