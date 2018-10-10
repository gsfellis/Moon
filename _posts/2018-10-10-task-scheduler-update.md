---
layout: post
title:  "Task Scheduler Update One"
date:   2018-10-10
excerpt: "During work on Enhancement 3, some changes occured to the way the Task Scheduler and overall project are organized."
tag:
- Noob SNHUbot
- milestone 3
- enhancement 2
- selenium
comments: false
---

While working on the MongoDB implementation for enhancement 3, I decided it was time to organize the additional modules I was importing into Noob SNHUbot.  I wanted to make sure as few files as necessary were held in the root folder of the project.

To accomodate this, I created another internal Python package for the bot to use, called `BotHelper`.  I've moved, and renamed, the former `bot_sched.py` to this package as `Scheduler.py`.  No other changes were made to the file itself. The folder structure now appears as below.

<figcaption>Project File Tree</figcaption>

```bash
noob_snhubot
├── BotHelper
│   ├── __init__.py
│   ├── MongoConnection.py
│   └── Scheduler.py
├── cmds
│   ├── __init__.py
│   ├── airspeed_velocity.py
│   ├── channels.py
│   ├── greet_user.py
│   ├── help.py
│   ├── my_name.py
│   ├── packtbook.py
│   └── roll.py
├── config.yml
├── LICENSE
├── noob_snhubot.py
├── README.md
└── requirements.txt
```

As can be seen, we keep the `noob_snhubot_py`, `requirements.txt`,`README.md`, `LICENSE`, and the new `config.yml`, introduced in enhancement 3, in the root folder.  `BotHelper` and `cmds` are now packages as indicated by the `__init__.py`.

The `BotHelper` `__init__.py` imports each of the scripts to allow the bot script to import them as if they were part of the `BotHelper`, instead of individual modules.

<figcaption>./BotHelper/__init__.py</figcaption>

```python
from .Scheduler import Scheduler
from .MongoConnection import MongoConnection
```

<figcaption>noob_snhubot.py</figcaption>

```python
from slackclient import SlackClient
from BotHelper import Scheduler
from BotHelper import MongoConnection
```
