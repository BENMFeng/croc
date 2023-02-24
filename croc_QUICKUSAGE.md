# Install:

```
git clone https://github.com/BENMFeng/croc.git
cd croc
git pull origin cyg
git checkout cyg
go build .
export PATH=$PATH:$PWD
```

# Sender TTY-1:
`$ croc --pass cygnus-2022 relay --ports 9009,9010,9011,9012,9013`

    [info]	2022/04/01 15:53:30 starting croc relay version v9.5.2-4a8c19b
    [info]	2022/04/01 15:53:30 starting TCP server on :9009
    [info]	2022/04/01 15:53:30 starting TCP server on :9011
    [info]	2022/04/01 15:53:30 starting TCP server on :9010
    [info]	2022/04/01 15:53:30 starting TCP server on :9012
    [info]	2022/04/01 15:53:30 starting TCP server on :9013

# Sender TTY-2:
`$ croc --pass cygnus-2022 --relay 172.16.40.242 send --ports 9009 ./croc`

    Sending 'croc' (5.4 MB)
    Code is: 6832-siren-street-marvin
    On the other computer run

    croc --relay 172.16.40.242 2187-mambo-modular-ibiza

# Sender TTY-3:
`$ croc --pass cygnus-2022 --relay 172.16.40.242 send --ports 9010 --code $(echo cygnus-$(echo $RANDOM `date`  | sha256sum | base64 | cut -c 18-30 |head -1)) ./croc`

    Sending 'croc' (7.6 MB)
    Code is: cygnus-kMDg2NTdiYjNl
    On the other computer run

    croc --relay 172.16.40.242 cygnus-kMDg2NTdiYjNl


# Receiver-1:
`$ croc --pass cygnus-2022 --relay data.cygnusbio.net 2187-mambo-modular-ibiza`

    Accept 'croc' (5.4 MB)? (Y/n) y

    Receiving (<-172.16.40.242:49948)
    100% |████████████████████| (5.4/5.4 MB, 6.862 MB/s)

# Receiver-2:
`$ croc --pass cygnus-2022 --relay data.cygnusbio.net cygnus-kMDg2NTdiYjNl`

    Accept 'croc' (5.4 MB)? (Y/n) y

    Receiving (<-172.16.40.242:49970)
    100% |████████████████████| (5.4/5.4 MB, 6.862 MB/s)