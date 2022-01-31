# layerz
Get container image's layers (Docker image [docker.io] / Podman image [quay.io|buildah] / dregistry)

## Usage
```
Get container image (OCI) layers                                      
USAGE: layerz <option> [image]                                                        
                                                                                  
Examples:                                                                          
       layerz -d alpine                                                               
       layerz -p quay.io/libpod/alpine                                                
       layerz -r docker.io/alpine                                                     
                                                                                  
Options:                                                                          
       -d, --docker   Get Docker image's layers (dockerhub, built from Dockerfile)
       -p, --podman   Get Podman image's layers (quay.io ...)                     
       -r, --remote   Get image's layers remotely (from a registry)               
       -h, --help     Show this help                                              
```

## Setup
```bash
git clone https://github.com/DeedWark/layerz && cd layerz
chmod +x layerz && cp layerz /usr/bin/layerz
```

## Examples
```bash
$> layerz -d alpine
/bin/sh -c #(nop)  CMD ["/bin/sh"]
/bin/sh -c #(nop) ADD file:9233f6f2237d79659a9521f7e390df217cec49f1a8aa3a12147bbca1956acdb9 in /

$> layerz -p quay.io/libpod/alpine
/bin/sh -c #(nop)  CMD ["/bin/sh"]
/bin/sh -c #(nop) ADD file:fe64057fbb83dccb960efabbf1cd8777920ef279a7fa8dbca0a8801c651bdf7c in /

$> layerz -r docker.io/alpine
/bin/sh -c #(nop) ADD file:9233f6f2237d79659a9521f7e390df217cec49f1a8aa3a12147bbca1956acdb9 in /
/bin/sh -c #(nop) CMD ["/bin/sh"]

$> layerz -r docker://docker.io/alpine
/bin/sh -c #(nop) ADD file:9233f6f2237d79659a9521f7e390df217cec49f1a8aa3a12147bbca1956acdb9 in /
/bin/sh -c #(nop) CMD ["/bin/sh"]

$> layers -r quay.io/libpod/alpine
/bin/sh -c #(nop) ADD file:fe64057fbb83dccb960efabbf1cd8777920ef279a7fa8dbca0a8801c651bdf7c in /
/bin/sh -c #(nop) CMD ["/bin/sh"]

$> layerz -r docker://quay.io/libpod/alpine
/bin/sh -c #(nop) ADD file:fe64057fbb83dccb960efabbf1cd8777920ef279a7fa8dbca0a8801c651bdf7c in /
/bin/sh -c #(nop) CMD ["/bin/sh"]
```
