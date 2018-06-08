# Setting VNC for raspberry pi

This repo is about how to set the **raspberry pi 3B** to auto boot the **VNCserver** for remote desktop control.

For the old version of raspberry pi, you may install **VNC** supported package, such as *tightvncserver*, to get the **VNC server** run first.

## Usage

### for raspberry pi
- Enable the VNC for raspberry <br/>
    ```
    sudo raspi-config
    ```
    selecting `9. Advanceed Options` -> `A5 VNC`-> `Yes`
- Add `vncboot` to `/etc/init.d` and add the exectuable file to boot configure <br/>
    ```
    sudo chmod 755 /etc/init.d/vncboot
    sudo update-rc.d vncboot defaults
    ```
- Reboot raspberry pi

### for your server
- Open your server's remote desktop (e.g.*remmina* for Ubuntu/Linux mint, *VNC Viewer* for Win, which support VNC)
- Set the configure for VNC connection (the port and user are set in the `vncboot`)
    ```
    VNC Server: <IP>:0
    Username: 'pi'
    Password: <your pw for user 'pi'>
    ```
    Save and connect

## Reference
[RPi VNC Server](https://elinux.org/RPi_VNC_Server)
