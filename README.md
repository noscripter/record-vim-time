# Readme

* Author: lvwenlong_lambda@qq.com
* Last Modified:CST 2015-08-24 13:16:39 星期一

## Intro

track how long you have been using VIM today

## About this project

* parse log file generated by [vim-activity-log][vim-plugin-myfork] and record how long you have spent on vim per day 
* so you need to have [vim-activity-log][vim-plugin-myfork] installed
* [vim-activity-log][vim-plugin-myfork] is forked from [here][vim-plugin-origin], I did some minor modification to make the log format more consistent.
* this program could (and perhaps should) be used together with `crontab`

## Installation

```bash
$ cabal sandbox init
$ cabal install
```

## Usage

you need to specify a folder to save log in `.vimrc`

```vimL
let g:activity_log_location = '~/.activity_vim/%Y/%m/%d.log'
```

then:

```bash
$ record-vim-time ~/.activity_vim
```
this should be what you'll see:

> Time you spent on VIM today: 03:11:37

there is the situation that: you opened vim, did some coding, then you walk away(to have lunch, for example) without closing vim and didn't save your buffer, then you get a very very long action interval, and the recorded active time 
would be much longer than the time you actually spent on coding, to avoid this, you can specify a `maxInterval` like this

```bash
$ record-vim-time ~/.activity_vim 1800
```

thus, intervals longer than 1800 seconds would be ignored


[vim-plugin-myfork]:https://github.com/Alaya-in-Matrix/vim-activity-log
[vim-plugin-origin]:https://github.com/AD7six/vim-activity-log

## TODO

* support more options, for example:
    * logs for a specific day
    * all logs

### License

Released under the WTFPL(DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE) license.


