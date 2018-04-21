# Script generated with Bloom
pkgdesc="ROS - HTTP Streaming of ROS Image Topics in Multiple Formats"
url='http://ros.org/wiki/web_video_server'

pkgname='ros-kinetic-web-video-server'
pkgver='0.0.7_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ffmpeg'
'ros-kinetic-async-web-server-cpp'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
)

depends=('ffmpeg'
'ros-kinetic-async-web-server-cpp'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
)

conflicts=()
replaces=()

_dir=web_video_server
source=()
md5sums=()

prepare() {
    cp -R $startdir/web_video_server $srcdir/web_video_server
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

