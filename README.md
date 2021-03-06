# Postfix newrelic

## Prerequisites

| Compatibility for...	| Requirements |
|-----------------------|--------------|
| Ruby                  | 1.8.7 (including REE), 1.9.2, 1.9.3, 2.0.0, and 2.1.0; JRuby 1.6 and above; Rubinius 2.x |
| OS                    | UNIX-like operating systems such as Linux, Solaris, Mac OS X |
| Security requirements | As a standard security measure for data collection, your app server must support SHA-2 (256-bit). SHA-1 is not supported. |


## Installation and Running

Download the [latest release](https://github.com/Micka33/postfix-newrelic/releases/latest)

```
wget https://github.com/Micka33/postfix-newrelic/archive/vX.tar.gz
unzip vX.tar.gz
cd postfix-newrelic-master
```
Install the plugin dependencies.
```
bundle install
```

Edit `config/newrelic_plugin.yml` and replace "YOUR_LICENSE_KEY_HERE" with your licence key.

Run it.
```
bundle exec ./newrelic_postfix_agent
```

## How it works

This plugin periodically check the postfix folders.  
It is not an event driven plugin so it might easily miss some mails.  
It's use is most intended to monitor the different queues to spot problems.  
You will need to run it with the appropriate privileges so it can access the postfix folders.

