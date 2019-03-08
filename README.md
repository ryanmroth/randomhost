# Random Host

Generate and set a random hostname on Linux on each boot.

## Installation

1. Copy randomhost to /usr/bin/ or another location included in your $PATH variable
2. Issue command: `chmod +x randomhost`
3. Copy randomhost.service to /etc/systemd/system/
4. Issue command: `systemctl enable newhostname`