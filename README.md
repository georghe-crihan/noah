# Noah

Noah is a Darwin subsystem for Linux, or "Bash on Ubuntu on Mac OS X". Noah is implemented as a hypervisor that traps linux system calls and translates them into Darwin's system calls. Noah also has an interpreter of ELF files so that binary executables of Linux run directly and flawlessly without any modifications.

<img src="https://github.com/linux-noah/noah/blob/master/images/screenshot.png" width="600">


I.e. it's effectively an OSX Linux Execution Flavour, similar to that of
FreeBSD Linuxolator, aka Linux Emulation, aka Linux ABI.

In other words, it's the exact reverse of the
[Linux Darling](https://github.com/darlinghq) project.

I am not using it actively for XWindow programs emulation, though it is fine
in the original version, it might work in your case. If it still doesn't,
then it's way better to use xhyve for that.

## TODO:
- [ ] Fix VMX exit reason: 2147483681, [ref](https://developer.apple.com/documentation/hypervisor/1469470-vmx_exit_reasons?language=objc)

  [Issue here](https://github.com/linux-noah/noah/issues/43)

  See [here](https://github.com/Solo5/solo5/issues/206)

  and [here](http://openbsd-archive.7691.n7.nabble.com/Calculate-the-frequency-of-the-tsc-timecounter-td323570.html)

- [ ] Create a macports equivalent
- [ ] Employ path translation tricks, similar to that of FreeBSD /compat/linux
- [ ] Maybe create a FreeBSD compatibility layer, for some rare commercial
FreeBSD binaries.
- [ ] Document noah command line options, maybe even create a manpage.
- [ ] Create CentOS suite for noahstrap

## References:
- [xhyve](https://github.com/mist64/xhyve)
- [Linux Darling project](http://www.darlinghq.org/source-code/)
- [Let your Mach-O fly](http://www.blackhat.com/presentations/bh-dc-09/Iozzo/BlackHat-DC-09-Iozzo-Macho-on-the-fly.pdf)
- [Dynamic Linking: ELF vs. Mach-O](http://timetobleed.com/dynamic-linking-elf-vs-mach-o/)
- [Dynamic symbol table duel: ELF vs Mach-O, round 2](http://timetobleed.com/dynamic-symbol-table-duel-elf-vs-mach-o-round-2/)
- [Dynamic Linking of Imported Functions in Mach-O](https://www.codeproject.com/Articles/187181/Dynamic-Linking-of-Imported-Functions-in-Mach-O)
- [Macho fly discussion](https://news.ycombinator.com/item?id=499163)
- [FreeBSD Linuxolator aka Linux ABI](https://www.freebsd.org/doc/handbook/linuxemu-advanced.html)


## Quick Start

Noah is installed via homebrew. On the first run, noah automatically downloads and installs a comprehensive linux environment in your home directory (by default, ubuntu 16.04 is installed in `~/.noah/tree`).
macOS Sierra or higher is required.

```console
$ brew install linux-noah/noah/noah
$ noah
```

## Hacking

See [HACKING.md](HACKING.md).

## LICENSE

Dual MITL/GPL, for all files without explicit notaiton.
