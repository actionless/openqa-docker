Copy `data.template` as `data` and change permissions.

Checkout repo with tests to `./data/tests/`.

Start the stack:
`docker-compose up`

Go to `https://localhost:8080/api_keys`, generate key and secret. Uncomment the `[openqa_webui]` and `[localhost]` sections in `data/conf/client.conf`, and fill in the key and secret.

>@TODO: restart worker?


Copy ISO to `./data/factory/iso` and execute.
```sh
docker exec openqaplayground_webui_1 /usr/share/openqa/script/client isos post ISO=openSUSE-13.2-DVD-x86_64.iso DISTRI=opensuse VERSION=13.2 FLAVOR=DVD ARCH=x86_64 BUILD=0001
```

Or add a job without posting iso:
```sh
docker exec openqaplayground_webui_1 /var/lib/openqa/script/client jobs post DISTRI=arch VERSION=2015.05 ARCH=x86_64 BUILD=0001 TEST=foo MACHINE=64bit FLAVOR=DVD DESKTOP=textmode ISO=archlinux-2015.05.01-dual.iso
```