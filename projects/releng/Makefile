include $(HOME)/.env

build:
	sudo podman build -t releng $(CURDIR)
down:
	sudo podman pod rm -f releng-dev
ps:
	sudo podman ps -pa
up:
	sudo podman pod create --name releng-dev
	sudo podman run -it -d --net host --name releng --pod releng-dev -v $(ROOTDIR)/releng:/srv yudocaa/releng
shell:
	sudo podman exec -it releng bash

start:
	sudo podman pod start releng-dev

stop:
	sudo podman pod stop releng-dev
