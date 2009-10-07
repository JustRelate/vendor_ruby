./configure --enable-shared --prefix /tmp/ruby
make -j4
make install
rsync -a /tmp/ruby/ linux/<version>
mkdir linux/<version>/include
cd linux/<version>/include
ln -s ../lib/ruby/1.8/i686-linux/{config,defines,intern,missing,ruby}.h .
cd -
