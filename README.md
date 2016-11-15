# chmod-stego
A PoC on passing data through UNIX file privilege numbers (RWX Triplets) 

## Happy Birthday My Friend!
Those 2 scripts have been written as a Birthday Present to a Beloved Friend. Business with this guy has been the reason I was introduced both to Security and Python and I owe him (and the rest of the group of sec-pythonistas) an awful lot of my personal development.



## What was the inspiration
This guy (https://en.wikipedia.org/wiki/Andrew_S._Tanenbaum _) had a weird idea in his awesome book about Operating Systems (https://en.wikipedia.org/wiki/Modern_Operating_Systems). In the Covert Channel Paragraph he described that everything in an OS can be used as covert channel, so all kinds of data breaches are possible. He gave an example about Privilege Bits of a file in UNIX as a covert channel. He concluded that it can be a very massive one as an unlimited number of files can be used to deliver bytes. Even files created in /tmp for that reason only.

## So what the Hell are those scripts?
Those are 2 python scripts doing just that. A Sender and a Receiver that both understand a minimal protocol of 1-way data transfer using only chmod's on files selected by the user. There is also an auto-synchronization mechanism of the Receiver using ticking!


## Helps would help
```
usage: Sender.py [-h] (--directory DIRECTORY | --files [FILES [FILES ...]])
                 [--delay DELAY]
                 message

positional arguments:
  message               Message to be transmitted. Can be the output of a
                        shell command if you use backticks (`) or $()
                        expression in double-quotes (""). Example: ./Sender.py
                        -d sample_files/ "$(cat /etc/passwd | head)"

optional arguments:
  -h, --help            show this help message and exit
  --directory DIRECTORY, -d DIRECTORY
                        Use all files in this directory in the order "ls" returns
                        them (BEWARE: MUST BE WRITABLE)
  --files [FILES [FILES ...]], -f [FILES [FILES ...]]
                        Use the listed files as in the order they are given
  --delay DELAY         Set the delay between the chmod's
```



## So what?
I can't think of any use cases out CTFs! Those scripts are intended to be a geeky Bday present. If you find any real use on them _please_ let me now!
