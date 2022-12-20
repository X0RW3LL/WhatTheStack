# WhatTheStack
Helper script for identifying bad characters based on Immunity's stack dump\
**TL;DR [Usage](#usage)**

## Prologue
I started my PEN-200 journey not too long ago. I've always loved buffer overflows, but absolutely *hated* dealing with bad character identification.\
I decided to change that as a way of giving back to the community, and possibly saving other members their time and hassle.

## What It Is
**WhatTheStack** can help you identify bad characters based on stack dump pasted from Immunity Debugger as-is.\
It can also generate a python-friendly array of bad characters.

## How It Works
There are two core operational modes:
- badchars
- payload

**badchars:** compares stack dump against all characters [0x00:0xFF]\
**payload:** compares stack dump against msfvenom shellcode

## Target Audience
PEN-200 Students, but everyone else is more than welcome to use it as they see fit

## Environment Setup
```sh
# Tip: Consider adding the cloned repo to your $PATH environment to call the script from anywhere

# clone the repo into a location of your choice
$ git clone https://github.com/X0RW3LL/WhatTheStack.git

# cd into the repo after it's been cloned locally
$ cd WhatTheStack

# grant execute permissions to the script
$ chmod +x wts
```

## Usage
The following usage examples assume running the script from inside the local repo
```
$ ./wts -h
usage: wts [-h] [-v] [-u] [-i badchars|payload] [-g] [-b <badchars>] [-x]

options:
  -h, --help           show this help message and exit
  -v, --version        print version number and exit
  -u, --update         update to the latest version

core functionality:
  -i badchars|payload  identify bad characters - use against (badchars) [0x00:0xff]
                       or generated (payload) shellcode
  -b <badchars>        generate a badchar-excluded array (case insensitive): ./wts -b
                       '\x0a\x3d'

visual:
  -g                   generate a variable containing all characters [0x00:0xff]
  -x                   show example stack dump
```
### badchar mode
[![wts-badchars.png](https://i.postimg.cc/VsBWNsRg/wts-badchars.png)](https://postimg.cc/jC27gbBn)
<<<<<<< HEAD
<<<<<<< HEAD
[![wts-badchars-ex.png](https://i.postimg.cc/hjt6bXZc/wts-badchars-ex.png)](https://postimg.cc/8FxZTzV0)
=======
[![wts-badchars-ex.png](https://i.postimg.cc/SKrCQ63m/wts-badchars-ex.png)](https://postimg.cc/678yYvBP)
=======
[![wts-badchars-ex.png](https://i.postimg.cc/hjt6bXZc/wts-badchars-ex.png)](https://postimg.cc/8FxZTzV0)
>>>>>>> d39d264 (Update screenshots)
[![edb-bc.png](https://i.postimg.cc/05n7bx4G/edb-bc.png)](https://postimg.cc/NLyKnhBL)
[![wts-edb-bc.png](https://i.postimg.cc/02Hm0nPb/wts-edb-bc.png)](https://postimg.cc/1fwf9pgQ)
>>>>>>> 89b9557 (Update screenshots (edb))

### payload mode
[![wts-payload1.png](https://i.postimg.cc/jSB8NMnh/wts-payload1.png)](https://postimg.cc/Sn77b7rX)
[![wts-payload2.png](https://i.postimg.cc/bYL3Ly2r/wts-payload2.png)](https://postimg.cc/QV9QdrmZ)
[![edb-payload.png](https://i.postimg.cc/VLNntpyx/edb-payload.png)](https://postimg.cc/K4d1S98f)
[![wts-edb-payload.png](https://i.postimg.cc/13nFCF3M/wts-edb-payload.png)](https://postimg.cc/VJw55dMb)

## FAQs
- **I noticed an `--update` option. How does this work?**
  - The script queries the GitHub repo for the [current_version](current_version) using the requests library. If versions mismatch, you're prompted to proceed. If you choose to do so, the script will pull the latest changes into your local repo
- **Should I be worried about potential backdoors?**
  - The short answer: no
  - The long answer: your concerns are valid, and I encourage everyone to practice due diligence by going through the code and keeping an eye out for changes. However, I would not 1) do something unethical, and 2) jeopardize my reputation by pulling off such a silly stunt
- **How do I report bugs?**
  - You may create an issue with all the relevant bits of information; full Traceback calls, pasted payload and stack dump, and screenshots
- **What about contribution?**
  - Contribution is highly encouraged. Create a PR and we may discuss it
- **How can I contact you?**
  - You may reach out via Discord: `X0RW3LL#6548`

## Credits
Special thanks to the entire Offensive-Security team, as well as the amazing community that's helped me through my journey :heart:

## Links
[Offensive-Security Official Website](https://www.offensive-security.com)\
[Offensive-Security Community Discord](https://offs.ec/discord)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/F1F3EFYS1)
