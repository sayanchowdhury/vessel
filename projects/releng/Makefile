include $(HOME)/.env

build:
	 podman build -t releng $(CURDIR)
down:
	 podman pod rm -f releng-dev
ps:
	 podman ps -pa
up:
	 podman pod create --name releng-dev
	 podman run -it -d --net host --name releng --pod releng-dev -v $(ROOTDIR)/releng:/srv yudocaa/releng
shell:
	 podman exec -it releng bash

start:
	 podman pod start releng-dev

stop:
	 podman pod stop releng-dev
