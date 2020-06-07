+++
title = "Bandit"
date = 2020-06-06T19:15:01+02:00
weight = 10
draft = true
+++

https://overthewire.org/wargames/bandit/

## SSH

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

---

### Level 0

#### Solution

```bash
cat readme
```

#### Password

```
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

---

### Level 1

#### Solution

```bash
cat ./-
```

#### Password

```
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

---

### Level 2

#### Solution

```bash
cat "spaces in this filename"
```

#### Password

```
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```

---

### Level 3

#### Solution

```bash
cd inhere/
cat .hidden
```

#### Password

```
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

---

### Level 4

#### Solution

```bash
file inhere/*
cat inhere/-file07
```

#### Password

```
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

---

### Level 5

#### Solution

```bash
find inhere/* -size 1033c
cat maybehere07/.file2
```

#### Password

```
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

###  Level 6

#### Solution

```bash
find / -user bandit7 -size 33c -group bandit6
cat /var/lib/dpkg/info/bandit7.password
```

#### Password

```
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

### Level 7


```bash

cat data.txt | grep millionth
millionth       
```

`cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

