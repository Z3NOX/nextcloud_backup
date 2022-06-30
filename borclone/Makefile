TMPDIR := $(shell mktemp -d)
ETC := "/etc"
RUNUSER := "root"

install: install-config install-systemd
	[ ! -d /usr/local/bin ] || install -Dm755 borclone /usr/local/bin/borclone
	rm -r ${TMPDIR}


install-config:
	[ -d ${ETC}/borclone.d ] || install -Dm755 -d ${ETC}/borclone.d
	[ -f ${ETC}/borclone.d/main.conf ] || install -Dm600 -o ${RUNUSER} borclone.conf ${ETC}/borclone.d/main.conf

install-systemd: systemd/*
	mkdir -p ${TMPDIR}/systemd
	for file in $^; do \
		sed "s/\$${USER}/${RUNUSER}/" $${file} > ${TMPDIR}/$${file}; \
	        [ ! -d ${ETC}/systemd/system ] || \
			install -Dm644  ${TMPDIR}/$${file} ${ETC}/systemd/system/; \
	done


uninstall:
	rm /usr/local/bin/borclone
	rm ${ETC}/borclone.d/main.conf
	rm ${ETC}/systemd/system/borclone-back@.timer
	rm ${ETC}/systemd/system/borclone-back@.service
	rm ${ETC}/systemd/system/borclone-up@.timer
	rm ${ETC}/systemd/system/borclone-up@.service
	rm ${ETC}/systemd/system/borclone-backup@.timer
	rm ${ETC}/systemd/system/borclone-backup@.service
	rmdir ${ETC}/borclone.d
	rm -r ${TMPDIR}

