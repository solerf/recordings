+++
title = 'Github use multiple ssh keys'
date = '2025-10-22T16:57:06+02:00'
draft = false
tags = ['git', 'ssh']
+++

Once ssh key(s)  already generated, as per [GitHub generate keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent),
they need to be configured at a `config` file under `~/.ssh` with:

```shell
Host THE_IDENTIFIER_OF_THE_HOST_1
  HostName github.com
  User git
  AddKeysToAgent yes
  IdentityFile ~/.ssh/target_key_1
  
Host THE_IDENTIFIER_OF_THE_HOST_2
  HostName github.com
  User git
  AddKeysToAgent yes
  IdentityFile ~/.ssh/target_key_2
```

Of course, change `Host` and `HostName` to what suits you better. 

Then to clone repositories from respective configured hosts:
```shell
git clone git@THE_IDENTIFIER_OF_THE_HOST_1:GIT_ORG/GIT_REPO_NAME.git
```

Or adding the remote for an existing repository:
```shell
git remote add origin git@THE_IDENTIFIER_OF_THE_HOST_1:GIT_ORG/GIT_REPO_NAME.git
```
