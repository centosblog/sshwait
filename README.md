sshwait
============

Just restarted a server? Tired of pressing up and enter while waiting for SSH to be accessible again? Then sshwait is for you! This script automatically waits for an SSH connection to become available before attempting to connect.

### Usage

    sshwait <SSH_OPTIONS> <SSH_USER@SSH_HOST>

Note: due to the crude way that arguments are parsed by this script, the above sequence of parameters is mandatory.

### Example Output

    ./sshwait ck@demo.centosblog.com
    SSH user: ck
    SSH host: demo.centosblog.com
    SSH options:
    
    Waiting for SSH connection
    .................
    SSH ready (waited for 111 seconds)
    
    ck@demo.centosblog.com's password:

### Supported systems

This has been tested on CentOS 6 using both BASH and ZSH shells. I'm quite certain it will work on other systems that have BASH 4+ or ZSH 4+ installed. Note - if you want to use this on OS X, you will need to change "nc" to "netcat"


### Installation

1. Clone this repo to your preferred directory (eg: /opt)

    `cd /opt && git clone https://github.com/centosblog/sshwait`

2. Ensure sshwait/sshwait is executable

    `chmod +x /opt/sshwait/sshwait`

3. To make it globally executable, you can either:

a. Use an alias:

`alias sshwait='/opt/sshwait/sshwait'`

b. Add it to /usr/local/bin:

`cp /opt/sshwait/sshwait /usr/local/bin`


### Installation of Dependencies

1. Install nc (no special repositories required, included in CentOS base repository):

`yum install nc -y`


### Bugs and Nuances

1. One annoyance that I am aware of is that the standard SSH port 22 is only available. I'll extend this out as an option later.


### Disclaimer

I'm not a programmer, but I do like to make things. Please use this at your own risk.


### License

The MIT License (MIT)

Copyright (c) 2014 Curtis K (www.centosblog.com)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
