# Under The Wire : Century 

https://underthewire.tech/century 

Century is a wargame hosted by UnderTheWire for people to learn the basics of PowerShell.

## A brief Write-Up

### Century 1 => 2 

The password for Century2 is the **build version** of the instance of PowerShell installed on this system.


```
$PSVersionTable

Ouputs : 
BuildVersion                   10.0.14393.5582 
```

### Century 2 => 3

The password for Century3 is the name of the built-in cmdlet that performs the wget like function within PowerShell **PLUS** the name of the file on the desktop.

You can get the name of the file by using : 

```
ls
```

In the desktop. 

In PowerShell the built-in cmdlet that performs the wget like function is : invoke-webrequest

### Century 3 => 4

The password for Century4 is the number of files on the desktop.

To get the number of files on the desktop :

```
(ls).count
```

### Century 4 => 5

The password for Century5 is the name of the file within a directory on the desktop that has spaces in its name.

I started typing : 

```
cat '.\Can You Open Me\'
```

And used autocomplete to find the answer.

### Century 5 => 6

The password for Century6 is the short name of the domain in which this system resides in **PLUS** the name of the file on the desktop.

To get the name of the file on the desktop: 

```
ls
```

The short name of the domain is : underthewire

### Century 6 => 7

The password for Century7 is the number of folders on the desktop.

The command I used : 

```
(ls).count
```

### Century 7 => 8

The password for Century8 is in a readme file somewhere within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.

To find the read me file I used this command : 

```
ls -Filter "*readme*" -File
```

On each directory and found it on the downloads directory. You can then use :

```
cat Readme.txt
```

### Century 8 => 9

The password for Century9 is the number of unique entries within the file on the desktop.

The name of the file on the desktop is called unique.txt, so I did : 

```
(cat .\unique.txt | Select-Object -Unique | Measure-Object).count
```

### Century 9 => 10

The password for Century10 is the **161st** word within the file on the desktop.

The file on the desktop is called Word_File.txt, so I did :

```
(cat .\Word_File.txt).Split(" ")[160]
```

### Century 10 => 11 

The password for Century11 is the **10th** and **8th** word of the Windows Update service description combined PLUS the name of the file on the desktop.

The name of the file on the desktop is : 110 

I used :

```
Get-Service
```

To find a list of services on the computer and I saw this line:

```
Stopped wuauserv Windows Update

```

So the name of the windows update service is wuauserv. Since I could not make new files on the computer I used powershell variables to store data : 

```
$description = (Get-WmiObject -Class Win32_Service -Filter "Name='wuauserv'").Description
$words = $description -split ' '

echo $words[7]
echo $words[9]
```

### Century 11 => 12 

The password for Century12 is the name of the hidden file within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.

I used : 

```
ls -force
```

On every directory and found the answer in the downloads directory.

### Century 12 => 13 

The password for Century13 is the description of the computer designated as a Domain Controller within this domain **PLUS** the name of the file on the desktop.

The name of the file on the desktop is : _things

To get the name of the computer designated as the Domain Controller:

```
Get-ADDomainController

Output:
Name : UTW
```

Then to get the description : 

```
Get-ADComputer -Filter {Name -Eq 'UTW'} -Properties description
```

### Century 13 => 14

The password for Century14 is the number of words within the file on the desktop.

The name of the file on the desktop is countmywords, so I did :

```
$words = (cat .\countmywords).split(' ')
$words.count
```

### Century 14 => 15

The password for Century15 is the number of times the word “polo” appears within the file on the desktop.

The name of the file on the desktop is countpolos, so I did :

```
$words = (cat .\countpolos).split(' ')
$polos = ($words | Where-Object { $_ -eq "polo" })
echo $polos
```

