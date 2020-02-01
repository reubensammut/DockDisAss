# DockDisAss

## Motivation

During the [Crack the Perimeter](https://www.offensive-security.com/ctp-osce/)
course offered by [Offensive Security](https://www.offensive-security.com/), we
had some modules where we were required to write assembly, assemble it and even
look at the resulting binary representation of the assembly code. Other times
when looking at already built exploits, in order to properly understand the
shellcode in the exploit, we needed to disassemble the bytes that make up the
shellcode.

One tool which I found really useful in both these cases is the
[Online x86 / x64 Assembler and Disassembler](https://defuse.ca/online-x86-assembler.htm)
by Taylor Hornby. This tool does both jobs very well and often times I had multiple
tabs with this tool open to try different things out. The interface is very simple
and I really found myself productive using it.

There were a couple of times where the disk this tool is hosted on, was full, and
could not process any further requests. This frustrated me, as if this happened
during the OSCE exam, I would have surely felt a bit uncomfortable using other
tools when I got really used to this one.

The sources for this tool are available on [Taylor's Github account](https://github.com/defuse/defuse.ca).
So I thought that, just in case this happens during the exam, I'll spin up a
Docker container which runs this awesome tool and I can continue working as
usual.

So, what I did here is extract the relevant files for this tool to work,
made slight modifications, removed some extra stuff and created a Dockerfile
which would host this tool.

## Building the container

After downloading this repository, build the docker image:

```bash
$ docker build -t dockdisass .
```

Then run the container:

```bash
$ docker run -d -p 8080:80 --name disass dockdisass
```

Once that is done, you can access it in your browser

![screenshot](../master/images/screenshot.png)

## Credits

This tool is the work of [Taylor Hornby](https://defuse.ca), so all credit goes
to him.
