Matlab installer wants to download installations file in /tmp and everytime installation fails due to lack of space

**Solution 1:**

Run the command inside Linux filesystem namespace


`sudo unshare --mount -- /bin/bash -c "mount -o bind,noexec,nosuid,nodev /home/USER/installationfiles /tmp && sudo -u USER ./matlab_R2018b_glnxa64/install"`

    
**Solution 2:**

Simply run:

`$ ./install -tmpdir /path/to/installation/destination`

N.B. remember to extract the matlab_RXXX_glnxaXX.zip in this way:
`unzip -X -K matlab_RXXX_glnxaXX`



If you have suggestions or betters workaround please suggest me them or add them here.



**Pietro Ciuffreda Fedora 36**

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0
International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
