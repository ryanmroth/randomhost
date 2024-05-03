
# Random Host

Create and assign a random hostname to a Linux system every time it boots up.


## Installation

  1. Clone the repository and navigate to its directory.
  ```bash
    git clone https://github.com/ryanmroth/randomhost.git 
    cd randomhost
  ```
  2. Copy the "randomhost" file to the "/usr/bin/" directory or any other location that is included in your $PATH variable:
  ```bash
  sudo cp randomhost /usr/bin
  ```
  >**Note**: *If copying "randomhost" to a location other than "/usr/bin", edit line 7 in "randomhost.service" accordingly*:
  >```diff
  >- ExecStart=/usr/bin/randomhost
  >+ ExecStart=/your/directory/randomhost
  >```

  3. Set the executable permission for the copied "randomhost" file:
  ```bash
  sudo chmod +x /usr/bin/randomhost
  ```

  4. Copy the "randomhost.service" file to the "/etc/systemd/system/" directory:
  ```bash
  sudo cp randomhost.service /etc/systemd/system
  ```

  5. Ensure the permissions of the "randomhost.service" file are 644:
  ```bash
  sudo chmod 644 /etc/systemd/system/randomhost.service
  ```

  6. Refresh the systemd systemctl daemon by executing:
  ```bash
  sudo systemctl daemon-reload 
  ```

  7. Enable the service by running:
  ```bash
  sudo systemctl enable randomhost
  ```

### Optional

Before depending on the boot process, you can manually initiate the service to verify that it operates as intended.

1. Start the service by executing:
```bash
sudo systemctl start randomhost
```
2. Verify the hostname has been changed by running:
```bash
hostname
```
3. Examine the changes to the "/etc/hosts" file:
```bash
cat /etc/hosts
```
