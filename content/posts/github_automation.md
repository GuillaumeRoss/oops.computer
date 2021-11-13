---
title: "Automating"
date: 2021-11-13T13:23:54-04:00
draft: false
tag: ["GitHub, startup, basics, automation"]
categories: ["Secure Startup"]

---

In [Safer GitHub Setup](safer-github-setup.md), we restricted access to multiple operations in GitHub:

* Creating users can be done by owners, and we have few of those.
* Managing teams also requires owners privileges.
* Creating repositories is impossible for regular users.

This is where the [GitHub Terraform Provider](https://registry.terraform.io/providers/integrations/github/latest/docs) comes in.

Using this provider, you can:

* Create repositories
	* Configure branch protection on those repositories
* Invite users
* Manage teams
* And much more...

By putting configuration files for this in a GitHub repo with the proper branch protection, now, everyone in your organization can invite new users, request changes to teams, and create repositories.

## Service Account
Automation requires service accounts. GitHub does not have the concept of a "service" account. All users are worldwide, and should represent people.

To ensure your automation does not depend on a specific person, you must create a service account of some kind.

1. Create an email address for this purpose on your email provider (*github-automation@your_org.pancakes*)
2. Create a GitHub account for it. Save the password in a password manager.
3. If you are using Single Sign-On (SSO), and requiring it, grant permission to this account to log in to your organization via SAML.
4. Create a [Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) for this service account.
5. Add an email address to the GitHub account that will go to a mailing list you will receive.
6. Disable SAML access and remove any email license you granted this service account. We don't want it to be used interactively in the future anyway, so why pay for it to receive email?

## Recommended Branch Protection

For a critical repository that allows modifying teams, users and repositories, it is important for someone in your security team, or any other team responsible for security , to approve the changes. Therefore, your GitHub configuration repository should:

* Require 2 code reviews
* Have [CODEOWNERs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) configured
* Have branch protection apply to administrators
* Require commit signing

```
# Require review from Security Team for all changes
* @yourorg/security
```


## Process

<div class="mermaid">
graph LR;
id1(User)
id3[(github-config-repo/feature-branch)]
id4[(github-config-repo/main)]
id2{Is Approved?}
id5(Build Pipeline)
id6(Terraform)
id7(GitHub APIs)
id8(GitHub Users)
id9(GitHub Teams)
id10(GitHub Repositories)
id11(Code Owners)
id12(Branch Protection)
id1--Changes Configuration-->id3
id3--PR-->id11
id11-->id2
id2--No-->id1
id2--Yes-->id4
id4--Build Trigger-->id5
id5--Runs-->id6
id6--Executes and applies-->id7
id7-->id8
id7-->id9
id7-->id10-->id12
</div>
