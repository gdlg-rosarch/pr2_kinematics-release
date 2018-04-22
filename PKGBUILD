# Script generated with Bloom
pkgdesc="ROS - This package provides a kinematics implementation for the PR2 robot. It can be used to compute forward and inverse kinematics."
url='http://ros.org/wiki/pr2_arm_kinematics'

pkgname='ros-kinetic-pr2-arm-kinematics'
pkgver='1.0.9_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-angles'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kdl-parser'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-tf-conversions'
'ros-kinetic-urdf'
)

depends=('ros-kinetic-angles'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kdl-parser'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-tf-conversions'
'ros-kinetic-urdf'
)

conflicts=()
replaces=()

_dir=pr2_arm_kinematics
source=()
md5sums=()

prepare() {
    cp -R $startdir/pr2_arm_kinematics $srcdir/pr2_arm_kinematics
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

