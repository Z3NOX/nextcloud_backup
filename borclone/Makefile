install:
	[ ! -d /usr/local/bin ] || install -Dm755 borclone /usr/local/bin/borclone
	[ -d /etc/borclone.d ] || mkdir /etc/borclone.d
	[ -f /etc/borclone.d/main.conf ] || install -Dm644 borclone.conf /etc/borclone.d/main.conf
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back@.timer /etc/systemd/system/borclone-back@.timer
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back@.service /etc/systemd/system/borclone-back@.service
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-up@.timer /etc/systemd/system/borclone-up@.timer
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-up@.service /etc/systemd/system/borclone-up@.service
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-backup@.timer /etc/systemd/system/borclone-backup@.timer
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-backup@.service /etc/systemd/system/borclone-backup@.service


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

