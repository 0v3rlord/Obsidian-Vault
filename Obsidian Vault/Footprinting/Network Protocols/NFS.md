**Ports: 111 TCP, 2049 TCP**

Network File System(**NFS**) has the same purpose as **SMB**. You can access files on the network as if they were part of the local system. 

Based on SUN-RPC/ONC-RPC (Open Network Computing Remote Procedure Call)

Can be used for [[Privilege Escalation]] by creating users on your local system that match the permissions and SUID of NFS. 
# Footprinting the Service

###### Show available NFS shares
```bash
showmount -e $TARGET
```

###### Mount NFS share
```bash
sudo mkdir target-NFS                                    # Create mount point
sudo mount -t nfs $TARGET:/ ./target-NFS -o nolock  # Mount NFS
sudo umount ./target-NFS                            # Unmount 
```


