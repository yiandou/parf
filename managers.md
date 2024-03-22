#Pacman options
Pacman meson build should be run with the following options:
~~~
mkdir -p /parf/manager/pacman
meson configure "-Droot-dir=/parf/manager/pacman"
~~~
This will set the root directory to /parf/manager/pacman, so that it will install files there and not screw up the system packages.
#Portage options
Portage meson build should be run with the following options::
~~~
mkdir -p /parf/manager/portage
cp -f portage/cnf/make.globals conf/portage/make.globals
meson configure "-Dsystem-wide=false -Deprefix=/parf/manager/portage -Dportage-base=/parf/manager/portage -Dportage-bindir=/parf/manager/portage/bin -Dportage-datadir=/parf/manager/portage/share" 
~~~
#Nix options
Nix building should be run with the following options:
~~~
mkdir -p /parf/manager/nix
autoreconf -vfi
./configure --prefix=/parf/manager/nix --with-store-dir-path=/parf/manager/nix/store --localstatedir=/parf/manager/nix/var
make
make install
~~~
