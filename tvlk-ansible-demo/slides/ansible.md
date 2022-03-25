💻 🆕 🎊

Install `zsh`

```bash
$ sudo apt install zsh

# change the default shell
$ chsh -s $(which zsh)
```

Install `oh-my-zsh`

```bash
$ curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh

# install zsh autosuggestion
$ git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.oh-my-zsh/plugins/zsh-autosuggestionsF
# then edit ~/.zshrc
# plugins=(git zsh-autosuggestions)
```

--

### Ansible?

Top Level:

```yaml
- hosts: localhost
  pre_tasks: ...
  vars: ...
  tasks: ...
```

Task:

```yaml
- name: string
  # some actions here e.g `apt:`
  apt: string
  tags:
    - list
    - of
    - tags
```

---

### SO MANY TASKS!

![Spongebob Panic GIF](https://c.tenor.com/kqmQWutuhuwAAAAC/spongebob-panicking.gif)

--

### Split Tasks

Or as JS devs — "Splitting into smaller chunks"

local.yml

```yaml [3-5]
- hosts: localhost
  pre_tasks: ...
  tasks:
    - include: tasks/zsh.yml
    - include: tasks/node.yml
```

[task].yml

```yaml
# just give it a name and what task it should run
- name: Install vim
  apt: name=vim
```

---

### Tags

```yaml [3-4]
- name: Install vim
  apt: name=vim
  tags:
    - install
```

---

### Vault

An AES256 encryption

```bash
$ ansible-vault [file_name]

# example
$ ansible-vault ./ssh/id_rsa
```

<img src="https://i.kym-cdn.com/photos/images/newsfeed/001/513/012/625.jpg" width="200">

---

### Thank you!
