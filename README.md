# Boring-routines
 This project was a inspiration from a instagram post https://www.instagram.com/p/CYbJ7drrqz_/?utm_source=ig_web_copy_link were a build engineer automated his boring time consuming tasks which all programmers deal everyday. It took 10 hours of googling,research,smashing,coffee breaks and little bit of swear words to pull this off in a imperfect but a working piece of code.
 
 
 ## Installation
 
 clone the repo and install requirements by running the command from requirements folder
 
 ``pip install -r requirements.txt``
 
 Edit the file supervisord.conf according to your system path. Customise your output and error logs. Supervisor is a client/server system that allows its users to control a number of processes on UNIX-like operating systems.(same as cron). Supervisor has been tested and is known to run on Linux (Ubuntu 18.04), Mac OS X (10.4/10.5/10.6), and Solaris (10 for Intel) and FreeBSD 6.1. It will likely work fine on most UNIX systems.

Supervisor will not run at all under any version of Windows.
For more, refer http://supervisord.org/introduction.html
 
 ## Usage
 start supervisor by
 
``supervisord``

Before you start the process, run the script "deal-with-my-wife.py". It needs to be attached to a telegram account. Its a one time setup.

 start process by
 
``supervisorctl``

 ## Troubleshooting
 
Supervisor logs errors and output. Try googling the errors. If still it doesnt work, IT WORKED ON MY MACHINE 🤷🏾‍♂️

## Insights and configurations

The program "need-coffee.py" triggers the coffee machine via a [MQTT protocol](https://mqtt.org/). You need to setup a [MQTT broker](https://mosquitto.org/) in a machine. The trigger from this program publishes a mqtt message to the coffee machine, in my case its a [Raspberry pi](https://www.raspberrypi.org/).

The folder "coffeemachine" contains the code which will be running on the Raspberry pi. This code receives the message via MQTT and enables a hardware pin on the pi and disables it after few secounds(considering the time to fill a cup of coffee).

The messaging platform used in this project is [Telegram](https://telegram.org/) and the mail platform is [gmail](https://mail.google.com/).

## what can and will be improved?

* using cron tab instead of supervisor.
* Checking the status of coffee machine (online/offline) before passing the MQTT message. If offline it sends a message that coffee machine is offline.
* Notifying the user when the coffee is ready.
* improving the code stucture.
* Writting a better documentation for this fun filled project.
