# How to have Docker running on Android (rootless!)

1. Get Termux from the official GitHub or F-Droid releases (NOT Play Store!)
2. Install git using `pkg install git`
3. Clone this repository using `git clone https://github.com/StickBrush/PADECAndroidDocker`
4. `cd AndroidDockerEasy`
5. `chmod +x install.sh bootup.sh`
6. `./install.sh`. This will open install the required software for the Alpine VM.
7. To boot up the VM, execute `./bootup.sh`. Login as `root` (password: `unicorngundam`).
8. Use Docker within the Alpine VM! (Wait a few minutes for it to initialize properly). You can turn off the VM using the `poweroff` command.

## How does this work?

This repo provides you an installation script for QEMU, a quick execution script and an Alpine VM which has been set up using [this wonderful gist from oofnikj](https://gist.github.com/oofnikj/e79aef095cd08756f7f26ed244355d62). This lets you use the image right away with minimum hassle to run Docker containers on your phone.

## Docker is not starting!

Try to check if Docker is started with `service docker status`. You can start it with `service docker start`, and start it during bootup using `rc-update add docker`.

### Docker is still not working!

Use `setsid containerd` followed by `setsid dockerd` to see if this solves your issue.
