install:
	[ ! -d /usr/local/bin ] || install -Dm755 borclone /usr/local/bin/borclone
	[ -f /etc/borclone.conf ] || install -Dm644 borclone.conf /etc/borclone.conf
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back.timer /etc/systemd/system/borclone-back.timer
	[ ! -d /etc/systemd/system ] || install -Dm644 systemd/borclone-back.service /etc/systemd/system/borclone-back.service


uninstall:
	rm /usr/local/bin/borclone
	rm /etc/borclone.conf
	rm /etc/systemd/system/borclone-back.timer
	rm /etc/systemd/system/borclone-back.service
