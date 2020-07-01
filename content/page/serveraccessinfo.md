---
subtitle: "Server Access Tool"
tags: [ssh,vnc,linux]
---

## Radiology Server Access

All of the imaging and medical patient data is located within UCSF Radiology encrypted Linux servers. Here is how to access them:

### List of Radiology servers

Please refer to the [full list of Radiology servers (requires UCSF login)][ucsfservers] for a comprehensive list of servers grouped by CPU and GPU resources.

---

Here are the two main ways to access the servers:

### SSH

#### Mac and Linux users

- Open a terminal and type the following:
  - `ssh username@servername.radiology.ucsf.edu -L 9XXX:localhost:9XXX`
  - For the above command make sure to replace the `username` with your own, the  `servername` with any of the [listed server names (requires UCSF login)][ucsfservers] and the `9XXX` with a number above `9020`
  - There will be a prompt for your UCSF password  

#### PC users

- Use [WSL], [PuTTY], [Cygwin] or any other SSH tool:
  - Use `servername.radiology.ucsf.edu` as the host name
  - Specify the local port forwarding, using the same number `9XXX`, higher than `9020`, both the source port and the destination port
  - There will be a prompt for your UCSF password

---

### VNC

Unlike SSH, VNC allows you to access a virtual display of the servers. This lets you browse through the file system and open visual applications such as Matlab and a web browser in a virtual operating system. Follow these steps to start a VNC session:

- Download and install [VNC Viewer][vncviewer].
- Once installed you will need to SSH to the server to which you will VNC into and type the following command into a terminal:
  - `myvncserver`
  - Towards the bottom of the output, take note of the last number as that will be the display number you will need to access the VNC server. Shown as `radiology.ucsf.edu:7` highlighted below.

![vncimage]

- Open VNC Viewer and type the server information in the following form:
  - e.g. `servername.radiology.ucsf.edu:7`
  - You will be prompted for your UCSF username and password.

---

#### Advanced

- Refer to the Scientific Computing Services (SCS) [official VNC tutorial][scsvnc] for more advanced options (requires UCSF login)

[ucsfservers]: https://ucsf.box.com/s/yx3hv4trm4kniy1in0op2y7nzeukouf2
[wsl]: https://docs.microsoft.com/en-us/windows/wsl/install-win10
[putty]: https://www.ssh.com/ssh/putty/download
[cygwin]: https://cygwin.com/install.html
[vncviewer]: https://www.realvnc.com/en/connect/download/viewer/
[vncimage]: /materials/vncserversample.png "VNC Output"
[scsvnc]: https://wiki.radiology.ucsf.edu/bin/view/SCS/Tutorials/RealVNCAdvanced/
