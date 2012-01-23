./configure --enable-shared --prefix /tmp/ruby
make -j4
make install
rsync -a /tmp/ruby/ linux/<version>

# für Ruby 1.8:
mkdir linux/<version>/include

cd linux/<version>/include

# für Ruby 1.8:
ln -s ../lib/ruby/1.8/i686-linux/{config,defines,intern,missing,ruby}.h .

# für Ruby 1.9
ln -s ruby-1.9.*/* .

cd -
