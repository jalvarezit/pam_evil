.PHONY: install clean install reinstall

package_name = pam_evil
flags = -lssl -lcrypto

install: ${package_name}.o
	ld ${flags} -x --shared -o /lib/x86_64-linux-gnu/security/${package_name}.so ${package_name}.o

${package_name}.o: ${package_name}.c
	gcc ${flags} -fPIC -c ${package_name}.c

clean:
	rm -rf ${package_name}.o

uninstall: clean
	rm -rf /lib/x86_64-linux-gnu/security/${package_name}.so 

reinstall: uninstall install
