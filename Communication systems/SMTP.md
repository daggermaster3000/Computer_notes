Simple mail transfer protocol


## Beispiel eines einfachen Anwendungsprotokolls

SMTP ( Simple Mail Transfer Protokoll ) auf Textbasis:

Verbindung öffnen: telnet smtp-server port
Befehle/Protokoll: HELO hostname
````shell
telnet smtp.uzh.ch 25 (the port)
MAIL from:email-address
RCPT to:email-address
DATA
text ... ( Beenden mit einem Punkt auf einer leeren Zeile. )
QUIT
````
example:

```shell
220 idsmtp02.uzh.ch ESMTP Fri, 18 Nov 2022 13:59:24 +0100
HELO dolli.physik.uzh.ch
250 idsmtp02.uzh.ch Hello dolli.physik.uzh.ch [10.28.233.134]
mail from: quillan.favey@uzh.ch
500 unrecognized command
mail from:quillan.favey@uzh.ch
250 OK
rcpt to:quillan.favey@uzh.ch
250 Accepted
data
354 Enter message, ending with "." on a line by itself
Hello world.
.
250 OK id=1ow0zs-0001XX-Hl
```


