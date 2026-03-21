# raspberry-pi
# How to setup a Raspberry Pi 3B Model from start to finnish

*Note: This guide applies the Diátaxis approach in documentation: https://diataxis.fr/.*

Author's note:
Frustrated by the lack of clear, logical setup guides for the Raspberry Pi 3b, I wrote this manual to provide a more accessible starting point for makers and computer hardware hobbyists.

This will be a headless setup for Raspberry Pi, meaning that you won't need a monitor, keyboard to set up this project. Just your laptop and the items below will do.

------------------------------------------------------------------------------

## What is a Raspberry Pi and what can you do with it

A Raspberry Pi is a tiny, inexpensive computer. For less than $50, it includes all the components of a standard PC (processor, USB ports, etc.), runs various operating systems, and can be used in many projects (home server, electronics, robotics, retro-gaming, and more).

<img width="405" height="270" alt="image" src="https://github.com/user-attachments/assets/056a5785-b292-4f9e-be33-e8e2df2fd65f" />

## Items you need
1. Raspberry Pi (for this project I will be using the Raspberry Pi 3 Model B)
2. 3.5 Inch (480x320) Touch Screen LCD Display
3. A power supply
4. A micro SD card (at least 32GB) + micro SD Card Adapter
5. Memory card reader for your laptop (especially if you're using a Macbook)

## How does it work
A Raspberry Pi is a small computer, so it works the same way as any PC. An operating system (Linux in general) is installed on the SD card, and it can be connected to a monitor, keyboard and mouse to control it.

For this project, I will be using the Raspberry Pi 3b model which includes these components:

<img width="900" height="889" alt="image" src="https://github.com/user-attachments/assets/940bce21-e2d6-43e3-a733-bc3da4d53c3b" />

1. USB ports: It has 4 USB ports, 2x USB 3.0 (faster) and 2x USB 2.0 (to plug a keyboard and mouse for example).
2. RJ45 port: Connect the Raspberry Pi to an Ethernet cable to get access to the Internet.
3. Audio: It’s an output port for speakers, but you can’t plug a micro into it directly.
4. HDMI: HDMI Output.
5. Power supply: a Raspberry Pi is typically powered via USB. The connector is also different based on the model you have, but it basically works with a phone charger.
6. Micro SD card slot: It’s on the back of the main board, and you can use similar cards as in your camera or smartphone (micro SD format).
7. Wireless card: Most models can use Wi-Fi and Bluetooth.
8. Processor: There’s a CPU on it just like on any computer. It’s a different architecture (ARM), which means not all systems can run on it, but it works the same way as on any PC.
9. Memory: Raspberry Pi comes with RAM, starting from 256 MB on the oldest model to 8 GB on the most powerful. About 4 GB to 8 GB is what you typically get on a laptop nowadays, so it’s pretty good.
10. The GPIO pins: The 40 pins on the top allow you to connect the Raspberry Pi to an electronic circuit or plug an extension card on top of it.
11. The camera port: You can plug a cheap camera module and use it in Python or other programming languages to build fun projects.
12. The display port: To connect the official monitor directly. But because there is an HDMI port on every model, you don’t really need this.

## What you can install on a Raspberry Pi
As a general rule, a Raspberry Pi will run with Raspberry Pi OS, a Linux distribution based on Debian and specifically created for it. But it can also run most Linux distributions, Android, Windows or systems created with special goals in mind (retro-gaming, media center, etc.).

When you use a Raspberry Pi for the first time, you’ll probably start with Raspberry Pi OS (formerly named Raspbian). It’s the ideal operating system, as it’s based on the most popular Linux distribution (Debian) and optimized for the Raspberry Pi, with all the tools most users need.

# Set up your micro SD card
Most MicroSD cards are supplied with a standard SD adapter. Carefully insert the MicroSD card into the designated slot at the base of the adapter.

Important: Ensure the write-protection switch (the "lock" slider) is toggled to the upward (unlocked) position. Confirm that the MicroSD card is fully seated within the adapter to ensure a proper connection.

![IMG_3017](https://github.com/user-attachments/assets/3cb47151-077f-4ac1-876e-0c5abf9f1502)

Once the card is secured in the adapter, insert the assembly into your preferred SD card reader
![IMG_3018](https://github.com/user-attachments/assets/e1aafacc-5822-48b1-870d-6fb4d789897f)


Finally, connect the adaptor to your laptop
![IMG_3019](https://github.com/user-attachments/assets/6c31a42c-7ece-4c68-8390-0fa8e30ede34)


# Headless Raspberry Pi setup

A headless setup is a way to set up Raspberry Pi OS, wifi, SSH, and VNC, all without plugging your Pi into a mouse, keyboard, or monitor. 

## Download Raspberry Pi Imager
With the SD card now plugged in through the adaptor to your computer, go to this website and download Raspberry Pi Imager: https://www.raspberrypi.com/software/.

Depending on your operating system, choose an appropriate version to download:
<img width="1165" height="746" alt="Screenshot 2026-03-21 at 15 00 43" src="https://github.com/user-attachments/assets/7aeb9e78-6033-4d68-8667-2d8bc9f2b80d" />

You will get a desktop app with this initial setup starting screen:
<img width="678" height="472" alt="Screenshot 2026-03-21 at 15 02 00" src="https://github.com/user-attachments/assets/ddce222e-7c32-496f-b69a-b40364be75ca" />

We will be using a Raspberry Pi 3 Model B for this project, so I will go ahead and select Raspberry Pi 3.

Next, you will be prompted to choose an Operating system to install on your Raspberry Pi.

<img width="668" height="472" alt="Screenshot 2026-03-21 at 15 03 17" src="https://github.com/user-attachments/assets/79ea0d75-be9d-4fb6-9910-7b5f56abdd50" />


I will choose to download the standard Raspberry Pi OS (64-bit), which is a Linux distribution based on Debian. 

Afterwards, you will be prompted to choose your storage device, which will be the Micro SD Card that I plugged in:

<img width="677" height="472" alt="Screenshot 2026-03-21 at 15 07 14" src="https://github.com/user-attachments/assets/aaee10b1-0296-434d-b54d-8c390c4a7b0a" />

As you can see it reads: Generic Mass-Storage Media (1000 GB), which is equal to 1Tb.

Important: Be careful to not deselect the option Exclude system drivers on the inner right corner. System drives typically contain files essential to the operation of your computer, and may include your personal files such as photos, videos and documents. Selecting the wrong drive will permanently erase data and can render your computer inoperable.

The next step is customization:

1. Choose your hostname: This is what the Raspberry Pi is going to display itself as over an internet network.

<img width="670" height="471" alt="Screenshot 2026-03-21 at 15 11 24" src="https://github.com/user-attachments/assets/8310c6fb-217a-4d83-b4b6-5a7dea476f63" />

2. Choose your location for localization: This is to suggest time zone and keyboard layout
<img width="670" height="469" alt="Screenshot 2026-03-21 at 15 15 11" src="https://github.com/user-attachments/assets/eaa48b26-e094-45ee-b1e5-e1308b9dd80d" />











-------------------------------------------------------------------------------
