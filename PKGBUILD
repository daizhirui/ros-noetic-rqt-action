# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - rqt_action provides a feature to introspect all available ROS action (from actionlib) types."
url='https://wiki.ros.org/rqt_action'

pkgname='ros-noetic-rqt-action'
pkgver='0.4.9'
_pkgver_patch=0
arch=('any')
pkgrel=3
license=('BSD')

ros_makedepends=(
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
)

ros_depends=(
	ros-noetic-rqt-msg
	ros-noetic-rqt-py-common
	ros-noetic-rospy
)

depends=(
	${ros_depends[@]}
)

_commit="fd461f410be6d7ef6beb5743251f0b4beba940e9"
_dir="rqt_action-${_commit}"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-visualization/rqt_action/archive/${_commit}.tar.gz")
sha256sums=('529ee4576ac4acb89b83b8356a79e031cb30132807c6ea83a7a37140a580ed3d')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
