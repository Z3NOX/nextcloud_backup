install:
	[ ! -d /usr/local/bin ] || install -Dm755 borclone /usr/local/bin/borclone
	[ -d /etc/borclone.d ] || mkdir /etc/borclone.d
	[ -f /etc/borclone.d/main.conf ] || install -Dm644 borclone.conf /etc/borclone.d/main.conf
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back@.timer /etc/systemd/system/borclone-back@.timer
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back@.service /etc/systemd/system/borclone-back@.service


uninstall:
	rm /usr/local/bin/borclone
	rm /etc/borclone.d/main.conf
	rm /etc/systemd/system/borclone-back@.timer
	rm /etc/systemd/system/borclone-back@.service
	rmdir /etc/borclone.d

