# fw-mesh-host 

This is a [Framework Laptop 13 Mainboard (11th Gen Intel® Core™)](https://frame.work/products/mainboard-11th-gen-intel-core?v=FRANFG000C) with an Intel Core i5 processor.

It's running Fedora and hosts virtual machines, such as [fw-mesh-vm-nixos](fw-mesh-vm-nixos.md) that run services for accessing, monitoring and administering the mesh.

It is also running a small [Caddy](https://caddyserver.com/) webserver along with a podman container of [librespeed](../../services/librespeed.md). The Caddy webserver reverse proxies to librespeed when it is queried as `http://speedtest.mesh`.