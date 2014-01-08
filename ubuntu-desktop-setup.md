# Ubuntu Destop Setup

* 12.04 LTS
* probably missing loads as I don't really use an ubuntu rig much


##GUI Update Manager
On initial install, allow the update manager to kick into action and install
any updates.

##Guest Additions
* install guest additions (under the devices menu) to allow full-screen
workings.
* restart for it to work

##Shared Folders
In VB machine preferences add a shared folder for the windows folder you want
to share, giving it the name shared.

`sudo mkdir /media/shared`

And to make the share auto-mount at boot

```sh
grep mount /etc/rc.local
# => mount -t vboxsf shared /media/shared
```

then find it in the 'file explorer', open the shared directory and press
'ctrl + d' to add a bookmark for it in
the finder sidebar.

##Sidebar
* add terminal
* loose LibraOffice+, ubuntu one

##terminal
* set profile:
  - run command as a login shell
  - unlimted scrollback
  - run 'screen' instead of my shell (so text reflows on resize)
  - untick Scrolling -> Use keystrokes to scroll alternate screen
* edit keyboard shortcuts
  * Terminal -> Reset and Clear -> Ctrl-k

##Firefox
* Addons: VimFx
* set home page to: https://www.google.co.uk/webhp?complete=0&hl=en
* about:config -> browser.newtab.url -> (set to home page url)

##My Developer tools
* run the provisioning scripts (`sudo ./provision_dev_essentials`, `sudo ./provision_dockerize`)
* add yourself to the docker group `sudo usermod -a -G docker <user>`
* import dotfiles `bash <(curl -sSL https://raw.github.com/roovo/dotfiles/master/scripts/bootstrap)`
* log out and in again to pick up the new permissions and dotfile stuff
