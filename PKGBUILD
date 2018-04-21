# Script generated with Bloom
pkgdesc="ROS - cv_camera uses OpenCV capture object to capture camera image. This supports camera_image and nodelet."
url='http://wiki.ros.org/cv_camera'

pkgname='ros-kinetic-cv-camera'
pkgver='0.3.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-camera-info-manager'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-opencv3'
'ros-kinetic-roscpp'
'ros-kinetic-roslint'
'ros-kinetic-rostest'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-camera-info-manager'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-opencv3'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=cv_camera
source=()
md5sums=()

prepare() {
    cp -R $startdir/cv_camera $srcdir/cv_camera
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

