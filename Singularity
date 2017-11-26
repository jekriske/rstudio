Bootstrap: shub
From: jekriske/r-base

%labels
  Maintainer Jeff Kriske
  Version v0.0.1
  Rstudio_Version 1.1.383
  R_Version 3.4.2

%setup
export SINGULARITY_DEFFILE_FROM='jekriske/r-base'

%help
  This will run Rstudio Desktop

%runscript
  exec rstudio

%post
  yum update -y
  yum install -y libxbcommon \
                 libxkbcommon \
                 libxkbcommon-x11 \
                 mesa-dri-drivers \
                 dejavu-sans-mono-fonts \
                 abattis-cantarell-fonts \
                 open-sans-fonts \
                 xorg-x11-server-utils \
                 https://download1.rstudio.org/rstudio-1.1.383-x86_64.rpm
  yum clean all && rm -rf /var/cache/yum
  cat <<EOT >> /etc/fonts/local.conf
    <match target="font">
    <edit name="autohint" mode="assign">
      <bool>true</bool>
    </edit>
    <edit name="hinting" mode="assign">
      <bool>true</bool>
    </edit>
    <edit mode="assign" name="hintstyle">
      <const>hintslight</const>
    </edit>
    <edit mode="assign" name="lcdfilter">
      <const>lcddefault</const>
    </edit>
    </match>
EOT
