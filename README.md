Copy `data.template` as `data` and change permissions.

Go to https://localhost:8080/api_keys, generate key and secret. Uncomment the `[openqa_webui]` and `[localhost]` sections in `data/conf/client.conf`, and fill in the key and secret.


Copy ISO to `/data/factory/iso` and execute.
```sh
/usr/share/openqa/script/client isos post ISO=openSUSE-13.2-DVD-x86_64.iso DISTRI=opensuse VERSION=13.2 FLAVOR=DVD ARCH=x86_64 BUILD=0001
```

