<h1>Creating Network Attached Storage with wired ethernet connection</h1>
  <h2>Introduction</h2>
    <p>Create NAS with your RPi and access files from any device.</p>
  <h2>Hardware you'll need</h2>
    <ol>
      <li>Raspberry Pi 4 (that's what I got)</li>
      <li>Micro SD card reader</li>
      <li>Your external hard drive for storage.</li>
    </ol>
  <h2>Software you'll need to install on your laptop or pc</h2>
    <ol>
      <li><a href="https://www.raspberrypi.com/software/">Raspberry Pi Imager</a></li>
      <li><a href="https://www.9bis.net/kitty/#!pages/download.md">KiTTY terminal to ssh from windows machine</a>, if you are on mac you are good.</li>
    </ol>
  <h2>Let's get geeky</h2>
    <h3>Baking your Pi</h3>
      <ol>
        <li>Insert Micro SD card into the reader. Plug your micro SD card reader to your laptop.</li>  
        <li>Open Imager -> Chose OS -> Raspberry Pi Os (Other) -> Raspberry Pi OS Lite (32 bit)</li>
        <li>Chose storage -> your micro SD card</li>
        <li>Click on settings gear ⚙️ icon -> enable ssh and leave wifi credentials empty.</li>
        <li>Write the OS</li>
      </ol>
    <h3>Frosting your Pi</h3>
      <ol>
        <li>Insert your micr SD in your RPi and connect it to ethernet cable, then switch it on. (Your RPi is now aliveeee)</li>
        <li>Log in to your internet router and checkout your RPi's IP address</li>
        <li>Open terminal or KiTTY and ssh into your RPi by typing: <code>ssh pi@[ip address of your pi]</code></li>
        <li>The default password is <code>raspberry</code></li>
        <li>Update and upgrade your pi using <code>sudo apt update && apt upgrade</code></li>
        <li>Install Open Media Vault using </br><code>wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash</code></li>
        <li>Rebood your Pi <code>sude reboot</code></li>
      </ol>
    <h3>Adding cherry on top (Open Media Vault settings)</h3>
      <ol>
        <li>Get your RPi's IP address again, it might have changed after installing OMV (Open media vault)</li>
        <li>Put the address in web browser and log into your OMV. </br>Default username: admin </br>Default Password: openmediavault</li>
        <li>Plug in your external hard drive to your RPi.</li>
        <li><b>Mount</b> your external hard drive by going to File Systems (located in left side menu). </br>Find your external hard drive and select it, then click on mount (located at the top) and then click on apply changes.</li>
        <li>Create a <b>shared folder</b> on your external hard drive by going to Access Rights Management -> Shared Folders -> Add</li>
          <ol>
            <li>Name: name your shared folder</li>
            <li>Device: your external hard drive</li>
            <li>Comment: Please write a meaningful comment to know what this shared folder represents.</li>
            <li>Then click on save and apply the changes.</li>
          </ol>
        <li>Go to Access Rights Management -> Shared Folders -> Privileges -> give your user and group Read/Write privileges. Save and apply the changes.</li>
        <li>Enable NFS and SMB Services and add the shared folder.</li>
      </ol>
  
  <h2>Resources</h2>
    <ul>
      <li><a href="https://www.youtube.com/watch?v=gyMpI8csWis&t=1059s&ab_channel=NetworkChuck">Network Chuck explains how to create NAS</a></li>
      <li><a href="https://pimylifeup.com/raspberry-pi-openmediavault/">Installing OpenMediaVault to a Raspberry Pi</a></li>
    </ul>
