KEY=CD9C0E84
DIST=trusty

clean:
	rm -vf debian/files
	rm -vfr debian/munin-plugins-rabbitmq
	rm -vf debian/munin-plugins-rabbitmq*

package:
	dpkg-buildpackage -A -us -uc
 
source:
	dpkg-buildpackage -S -k$(KEY)

source_no_sign:
	dpkg-buildpackage -S -us -d
 
upload_to_ppa:
	dput ppa:lordgaav/munin-plugins-rabbitmq "$(CHANGES)"

pbuild:
	pbuilder-dist "$(DIST)" "$(CHANGES)"
