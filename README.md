# layerz
Get container image's layers (Docker image [docker.io] / Podman image [quay.io|buildah] / dregistry)

# Usage
```bash
Get container image (OCI) layers                                      
USAGE: $0 <option> [image]                                                        
                                                                                  
Example:                                                                          
       $0 -d alpine                                                               
       $0 -p quay.io/libpod/alpine                                                
       $0 -r docker.io/alpine                                                     
                                                                                  
Options:                                                                          
       -d, --docker   Get Docker image's layers (dockerhub, built from Dockerfile)
       -p, --podman   Get Podman image's layers (quay.io ...)                     
       -r, --remote   Get image's layers remotely (from a registry)               
       -h, --help     Show this help                                              
```
