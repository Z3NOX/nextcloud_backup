TMPDIR := $(shell mktemp -d)
RUNUSER := "root"

install: install-config install-systemd
	[ ! -d /usr/local/bin ] || install -Dm755 borclone /usr/local/bin/borclone
	rm -r ${TMPDIR}


install-config:
	[ -d /etc/borclone.d ] || install -Dm755 -d /etc/borclone.d
	[ -f /etc/borclone.d/main.conf ] || install -Dm600 -o ${RUNUSER} borclone.conf /etc/borclone.d/main.conf

install-systemd: systemd/*
	mkdir -p ${TMPDIR}/systemd
	for file in $^; do \
		sed "s/\$${USER}/${RUNUSER}/" $${file} > ${TMPDIR}/$${file}; \
	        [ ! -d /etc/systemd/system ] || \
			install -Dm644  ${TMPDIR}/$${file} /etc/systemd/system/; \
	done


uninstall:
	rm /usr/local/bin/borclone
	rm /etc/borclone.d/main.conf
	rm /etc/systemd/system/borclone-back@.timer
	rm /etc/systemd/system/borclone-back@.service
	rm /etc/systemd/system/borclone-up@.timer
	rm /etc/systemd/system/borclone-up@.service
	rm /etc/systemd/system/borclone-backup@.timer
	rm /etc/systemd/system/borclone-backup@.service
	rmdir /etc/borclone.d
	rm -r ${TMPDIR}

