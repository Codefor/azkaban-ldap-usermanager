Azkaban Ldap UserManager
========================
enhanced ldap usernamager. 基于LDAP认证，基于XML授权

Copied and Improved Via https://github.com/researchgate/azkaban-ldap-usermanager

This plugin enables ldap authentication for the Azkaban workflow manager (https://azkaban.github.io/)

This plugin is work in progress, configuration options may change.

Installation
------------

Build the plugin

```
gradle build
```

and place the created jar from ./build/libs into the ./extlib folder of Azkaban (see also http://azkaban.github.io/azkaban/docs/latest/#user-manager) for details.

In your azkaban.properties file set the UserManager to the new Ldap one:

```
user.manager.class=com.ymt.azkaban.user.LdapUserManager
```

Configuration
-------------

The following configuration options are currently available:

```
user.manager.ldap.host=ldap.example.com
user.manager.ldap.port=636
user.manager.ldap.useSsl=true
user.manager.ldap.userBase=dc=example,dc=com
user.manager.ldap.userIdProperty=uid
user.manager.ldap.emailProperty=mail
user.manager.ldap.bindAccount=cn=read-only-admin,dc=example,dc=com
user.manager.ldap.bindPassword=password
user.manager.ldap.allowedGroups=azkaban-ldap-group
user.manager.ldap.groupSearchBase=ou=Groups,dc=example,dc=com
user.manager.xml.file=conf/azkaban-users-auth.xml
```
