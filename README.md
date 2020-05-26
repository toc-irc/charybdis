# Ubuntu 18.04 LTS install
sudo apt-get install -y libtool m4 automake bison flex
sudo su ircd
git clone https://github.com/charybdis-ircd/charybdis.git
cd charybdis
./autogen.sh
./configure --enable-openssl --with-custom-branding=TOC --with-custom-version=ONE --with-nicklen=32 --prefix=$HOME/ircd
mkdir ~/ircd/modules/disabled
mv ~/ircd/modules/autoload/m_operspy.so ~/ircd/modules/disabled
mv ~/ircd/modules/extentions/m_webirc.so ~/ircd/modules/autoload/m_webirc.so
