# aria2-static-builds

This repository is for distributing binaries only. This build works on Windows XP SP3 well, so I make this copy.

Original source code: <https://git.q3aql.dev/q3aql/aria2-static-builds>

### aria2 1.37.0 builds (with OpenSSL)

_Note: The error with `bcrypt.dll` library on `Windows XP` has been fixed._

_Info: In this version, the Windows builds include manifest for Windows 10 (Contributed by [eladkarako](https://github.com/eladkarako))_

### How to install

* **GNU/Linux instructions:**
  
  * Open the terminal and type the following commands:

      ```shell
      tar jxvf aria2-1.37.0-linux-gnu-[arch]-build1.tar.bz2
      cd aria2-1.37.0-linux-gnu-[arch]-build1
      sudo make install
      ````

* **Windows instructions:**
  
  * Unzip the package with [7-zip](http://www.7-zip.org/) or [Winrar](http://www.rarlab.com/).
  * Copy the files to a folder. For example: `C:\Program Files\aria2`
  * Add the folder to [PATH](https://www.google.es/search?q=add+folder+to+PATH+on+Windows) variable.

### CA Certificates on Windows (HTTPS)

To perform downloads using **HTTPS**, is necessary the ca-certificates. For default, Linux binaries read the certificates from **/etc/ssl/certs/ca-certificates.crt**, but with Windows binaries are necessary define the path of certificates.

You can define the path of the certificates permanently using `aria2.conf` located on `C:\Users\<user>\.aria2\`. If you use Windows XP, the file is located on `C:\Documents and settings\<user>\.aria2\`. For example, you just have to add the following line:

```shell
ca-certificate=C:\Program Files\aria2\certs\ca-certificates.crt
```

If you prefer load the certificates manually, you can use the following command:

```shell
C:\PATH\> aria2c --ca-certificate=<PATH-TO-CERTIFICATE> <URL>
```

Also, is possible disable the use of certificates with the following command:

```shell
C:\PATH\> aria2c --check-certificate=false <URL>
```

### Used external libraries

* <http://www.zlib.net/>
* <https://libexpat.github.io/>
* <https://c-ares.org/>
* <http://www.sqlite.org/>
* <http://www.openssl.org/>
* <http://www.libssh2.org/>

### External links

* [aria2 homepage](https://aria2.github.io/)
* [aria2 documentation](https://aria2.github.io/manual/en/html/)
* [aria2 source code (Github)](https://github.com/aria2/aria2)
