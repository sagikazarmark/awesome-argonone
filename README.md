# Awesome Argon ONE

[Argon ONE](https://www.argon40.com/argon-one-v-2-case-for-raspberry-pi-5.html) is a case for [Raspberry Pi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/) by [Argon40](https://www.argon40.com/argon-one-v-2-case-for-raspberry-pi-5.html).

It's a popular case, because it comes with fairly good cooling options (good passive cooling + fan),
a power button to power up and shut down the Pi, remote control via IR and a couple other cool features out of the box.

There is also an M.2 variant of the case that lets you mount an M.2 SATA SSD in the case and even boot from there!

All these features come at a prices of course, but if you need a media center with great cooling, HDMI output and remote control,
it's probably worth it.

(Look for more thorough reviews and tests below)


## Contents

- [How it works?](#how-it-works)
- [Is it awesome enough?](#is-it-awesome-enough)
- [Software](#software)
    - [Replacements](#replacements)
        - [Python](#python)
        - [C](#c)
        - [Go](#go)
        - [Rust](#rust)
        - [Docker](#docker)
    - [argon1.sh](#argon1.sh)
    - [Misc](#misc)
- [Reviews, tutorials](#reviews-tutorials)


## How it works?

Assembling the case is quite simple (although it requires more screws than any other Pi case out there).
Once you are done with assembling the case and installing the OS,
you need to install a few components on the Pi in order to control fan speed, use the power button and the IR remote.

The necessary components can easily be installed using the following script:

```bash
curl https://download.argon40.com/argon1.sh | bash
```

**Note:** The script only supports Raspbian and Ubuntu.


## Is it awesome enough?

It's a perfectly valid question to ask whether a Raspberry Pi case deserves an "awesome" page.
These pages tend to list exceptional content and materials for a given topic (eg. software libraries for a programming language).

After spending a couple days with the case and the software, I was still unhappy about it.

First of all, I prefer managing my Pis with Ansible (insert your favorite configuration management tool here)
and this script is everything, but Ansible compatible. It works (and even comes with an uninstall option which is nice),
but the installation procedure under the hood is interesting at best (it's probably a real pain to test).

Bottom line is: I started to create an Ansible role for the contents of the install script.

Out of curiousity, I looked for other people's work on the internet and I found tons of
replacements for the "official" Argon ONE software. I tried some of them,
but so far I didn't find one that checked all the boxes.

So I decided to compile a list of the available materials,
just to gather some information and learn something from the existing implementations.

With that knowledge I'll be able to create the ONE implementation that is perfect.

Mandatory xkcd:

![How standards proliferate?](https://imgs.xkcd.com/comics/standards.png)

If anyone is interested, here is the checklist for my ideal Argon ONE software:

- [ ] Cross-platform: supports Debian, Ubuntu, Raspbian, Arch, CentOS, DietPi, Kali, insert Pi OS here, etc
- [ ] Comes with DEB, RPM, PKGBUILD
- [ ] Can be downloaded from APT repos _(optional)_
- [ ] Comes with an Ansible role _(optional)_
- [ ] Doesn't have dozens of open, unanswered, 1 year old issues and PRs

To answer my own question: it started as a little joke, but it looks like this case is popular enough that a link collection
like this might be useful to someone, so here it is.


## Software

Argon ONE software components.

### Replacements

Replacements for the "official" Argon ONE components.

#### Python

- [spapadim/argon1](https://github.com/spapadim/argon1): Written from ground up with much nicer configuration, D-Bus integration, LXPanel plugin, DEB package and a lot more...sadly with a lot of open issues and PRs.
- [Overbryd/argononed](https://github.com/Overbryd/argononed): Simple alternative to the official software.
- [markrad/ArgonOned](https://github.com/markrad/ArgonOned): MQTT support for the Argon ONE service.

#### C

- [RenHoekNL/argonONE](https://github.com/RenHoekNL/argonONE): Standalone daemon for Argon ONE.
- [DarkElvenAngel/argononed](https://gitlab.com/DarkElvenAngel/argononed): A replacement daemon for Argon ONE.
- [wulfy23/rpi4-argononed-fork](https://github.com/wulfy23/rpi4-argononed-fork): A replacement daemon for Argon ONE.

#### Go

- [samonzeweb/argononefan](https://github.com/samonzeweb/argononefan): Argon ONE fan speed control written in Go (claiming to use less memory than Python).
- [panyingyun/argonone](https://github.com/panyingyun/argonone): Another Argon ONE fan speed control.

#### Rust

- [lmariscal/argonone-rs](https://github.com/lmariscal/argonone-rs): Argon ONE fan speed control.
- [tonyfettes/argonone](https://github.com/tonyfettes/argonone): Argon ONE fan speed and power button control.
- [jonlamb-gh/rpi4-argon-fan-controller](https://github.com/jonlamb-gh/rpi4-argon-fan-controller): Another Argon ONE fan control daemon.
- [Eraden/argonfand](https://github.com/Eraden/argonfand): Another Argon ONE fan control daemon.

#### Docker

- [jmercha/docker-argonone](https://github.com/jmercha/docker-argonone): Argon ONE daemon running in a Docker container.

### argon1.sh

Copies of the original `argon1.sh` script.

- [wimpysworld/argon1-ubuntu](https://github.com/wimpysworld/argon1-ubuntu): Much nicer install script than the original adding Ubuntu 20.04 support.
- [trainmeditations/argon1](https://github.com/trainmeditations/argon1): Another install script with nicer coding style.
- [damaex/argonone](https://github.com/damaex/argonone): Install script with Ubuntu 20.04 support.
- [induna-crewneck/argon1-dietpi](https://github.com/induna-crewneck/argon1-dietpi): Install script with DietPi support.
- [gwylanscheeren/argonone_dietpi](https://github.com/gwylanscheeren/argonone_dietpi): Install script with DietPi support.
- [kounch/argonone](https://github.com/kounch/argonone): Arch Linux package.
- [tomjo/argonone-centos](https://github.com/tomjo/argonone-centos): Install script with CentOS support.
- [michacode/Argonone-Retropie](https://github.com/michacode/Argonone-Retropie): Install script with Retropie support.
- [ashstrahle/ArgonOneRPI4Kali](https://github.com/ashstrahle/ArgonOneRPI4Kali): Argon ONE fan control for Kali.
- [preparationh67/argononeplus](https://github.com/preparationh67/argononeplus): Refactored version of the official Argon ONE software.
- [lewishazell/raspberrypi-argonone](https://github.com/lewishazell/raspberrypi-argonone): Refactored version of the official Argon ONE software.
- [anrihaglund/argon1](https://github.com/anrihaglund/argon1): Yet another copy of the install script.
- [Cyd0n1a/argon-one-case-functionality](https://github.com/Cyd0n1a/argon-one-case-functionality): Yet another copy of the install script.
- [okunze/Argon40-ArgonOne-Script](https://github.com/okunze/Argon40-ArgonOne-Script): Yet another copy of the install script.
- [moosedookie/ArgonOne](https://github.com/moosedookie/ArgonOne): Yet another copy of the install script.

### Misc

Other Argon ONE related components.

- [Jonesyj83/PiHole-ArgononeFanSpeed](https://github.com/Jonesyj83/PiHole-ArgononeFanSpeed): PiHole integration.
- [vrischmann/argonone](https://github.com/vrischmann/argonone): Argon ONE fan speed control written in [Zig](https://ziglang.org/).
- [DarkElvenAngel/argonone-applet](https://gitlab.com/DarkElvenAngel/argonone-applet): A companion applet for [Argon ONE Daemon](https://gitlab.com/DarkElvenAngel/argonone-applet).


## Reviews, tutorials

Reviews about the case and tutorials about assembling and using it.

- [Argon One M.2 Raspberry Pi Case - SSD on your Pi 4!](https://www.youtube.com/watch?v=rLBdi8B5Wgk) (by Jeff Geerling)
- [Argon One M.2 Raspberry Pi SSD Case Review](https://www.jeffgeerling.com/blog/2021/argon-one-m2-raspberry-pi-ssd-case-review) (by Jeff Geerling)
- [Is This The Best Raspberry Pi 4 Case? The New Argon One M.2 - Review](https://www.youtube.com/watch?v=LLc4pF3jZQg)
- [Installing k3os on a Raspberry Pi with an Argon case ](https://tinkerlab.fr/202102d-Install-k3os-on-raspberry-pi/)
- [Argon-ONE-i2c-Codes](https://github.com/Argon40Tech/Argon-ONE-i2c-Codes)


## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.
