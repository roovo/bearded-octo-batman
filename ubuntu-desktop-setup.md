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

##Sidebar
* add terminal
* loose LibraOffice+, ubuntu one

##Proxy stuff
So that `sudo apt-get ...` respects proxy settings, the proxy env vars need
to be kept when sudoing:

```sh
sudo visudo     # and paste in: Defaults env_keep = "http_proxy https_proxy ftp_proxy"
```

##My Developer tools
* run the provisioning scripts
```sh
sudo -s
bash <(curl -sSL https://raw.github.com/roovo/bearded-octo-batman/master/provision_dev_essentials)
bash <(curl -sSL https://raw.github.com/roovo/bearded-octo-batman/master/provision_dockerize)
```
* add yourself to the docker group `sudo usermod -a -G docker <user>`
* import dotfiles `bash <(curl -sSL https://raw.github.com/roovo/dotfiles/master/scripts/bootstrap)`
* log out and in again to pick up the new permissions and dotfile stuff

##terminal
* set profile:
  - run command as a login shell
  - run 'screen' instead of my shell (so text reflows on resize)
  - unlimted scrollback
  - untick Scrolling -> Use keystrokes to scroll alternate screen
* edit keyboard shortcuts
  * Terminal -> Reset and Clear -> Ctrl-k

##Shared Folders
In VB machine preferences add a shared folder for the windows folder you want
to share, giving it the name shared.

On ubuntu create the mount point:

`sudo mkdir /media/shared`

And to make the share auto-mount at boot

```sh
grep mount /etc/rc.local
# => mount -t vboxsf shared /media/shared
```

then find it in the 'file explorer', open the shared directory and press
'ctrl + d' to add a bookmark for it in
the finder sidebar.

##Firefox
* Enter manual proxy settings
* Addons: VimFx, QuickProxy
  - to use QuickProxy: ctrl-/ toggles the Add-on bar
    or enable it by right clicking in emnpty bit of tab bar
* set home page to: https://startpage.com
* about:config -> browser.newtab.url -> (set to home page url)
* add startpage as the defaulf search in Firefox
  - click add to firefox link under search box on home page
