# Running kexec on DigitalOcean
So, DigitalOcean doesn't let you run a custom kernel on your droplet, but you can get around it by using kexec.

## How it works
1. Loads kernel into memory
2. Calls kexec syscall
3. Black magic happens
4. Your new kernel boots
5. ???
6. PROFIT!

## What you do
```bash
kexec -l /path/to/kernel --initrd=/path/to/initrd --reuse-cmdline
kexec -e
```

## Why?
- grsecurity on shell hosts

## On shell hosts
- We don't kexec at boot-time just in case Something Bad(TM) happens (this makes it easier to fix)
- So you need to run those steps above when you reboot a shell host
