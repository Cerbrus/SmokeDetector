SmokeDetector
=============

[![Build Status](https://travis-ci.org/Charcoal-SE/SmokeDetector.svg?branch=master)](https://travis-ci.org/Charcoal-SE/SmokeDetector) [![Circle CI](https://circleci.com/gh/Charcoal-SE/SmokeDetector.svg?style=shield)](https://circleci.com/gh/Charcoal-SE/SmokeDetector) [![codecov](https://codecov.io/gh/Charcoal-SE/SmokeDetector/branch/master/graph/badge.svg)](https://codecov.io/gh/Charcoal-SE/SmokeDetector)


Headless chatbot that detects spam and posts it to chatrooms. Uses [ChatExchange](https://github.com/Manishearth/ChatExchange), takes questions from the Stack Exchange [realtime tab](http://stackexchange.com/questions?tab=realtime), and accesses answers via the [Stack Exchange API](http://api.stackexchange.com/). 

Example [chat post](http://chat.stackexchange.com/transcript/11540?m=17962164#17962164):

![Example chat post](http://i.stack.imgur.com/d8pbW.png)

User documentation is in the
[GitHub wiki](https://github.com/Charcoal-SE/SmokeDetector/wiki).

To set up, use

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"

git clone https://github.com/Charcoal-SE/SmokeDetector.git
cd SmokeDetector
git submodule init
git submodule update
sudo pip install -r requirements.txt --upgrade
pip install -r --user user_requirements.txt --upgrade
```

Next, copy `config.sample` to a new file called `config`, and edit the values required.

To run, use `nocrash.py` or `python nocrash.py` (preferably in a daemon-able mode, like a `screen` session.)
You can also use `python ws.py`, but then SmokeDetector will be shut down after 6 hours; when running from `nocrash.py`, it will be restarted. (This is to be sure that closed websockets, if any, are reopened)

Note that SmokeDetector is written in Python 2, so you may have to explicity run `python2` if Python 3 is the default version of Python on your distro.

You can run `. ChatExchange/setp.sh` to set local environment variables so that you don't have to log in every time. 

SmokeDetector only supports Stack Exchange OpenIDs for now.

## License

Licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.
