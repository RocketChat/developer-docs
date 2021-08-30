# Possible Errors

These are the possible errors you can encounter while setting up local environment.

1. python-minimal has no installation candidate
   
   Solution-
   *  First run sudo -i to run commands as root
   *  Now make a copy of sources.list file by mv /etc/apt/sources.list /etc/apt/sources.list_stor
   * Then update packages apt-get update
   * Now edit sources.list file
   * Open file by vi /etc/apt/sources.list
   * Press i to change into insert mode
   * Copy paste this inside
   
   `deb http://archive.ubuntu.com/ubuntu bionic main restricted universe multiverse
   deb http://archive.ubuntu.com/ubuntu bionic-security main restricted universe multiverse
   deb http://archive.ubuntu.com/ubuntu bionic-updates main restricted universe multiverse
   deb http://mirror.kakao.com/ubuntu focal-security main restricted
   deb http://mirror.kakao.com/ubuntu focal-security universe
   deb http://mirror.kakao.com/ubuntu focal-security multiverse`
   * Press shift+esc and type :x and enter to save sources file
   * Run apt-get update again.
   * Run apt-get install python
   * Then come back to main terminal and run sudo apt install python-minimal.
