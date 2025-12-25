FROM almalinux:8
# ENTRYPOINT defines the executable, 
# and CMD provides default arguments 
# (so this runs: ping -c5 yahoo.com).
CMD ["yahoo.com"]
ENTRYPOINT [ "ping", "-c5"]

#Override CMD by passing new args to `docker run` 
# (e.g., `docker run <image> google.com` runs: ping -c5 google.com).