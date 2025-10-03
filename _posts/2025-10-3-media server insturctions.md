---
layout: post
title:  "media server instructions"
date:   2025-10-3 11:17:14 -0400
categories: fun
---

Here I will give instructions on how to access my media server. Please understand that the media server is only open to friends and loved ones for now (this is because i am afraid of what might happen to my local network).

---
{: data-content="philosophy"}

I don't know about you but I personally am sick and tired of the way media is consumed in this modern age. I don't like how spotify and netflix take things away from me and I would like to avoid this if at all possible. I started this project originally so that I could upload my CD collection for online streaming. Turns out the media server thing that I used - jellyfin - can host movies, TV, photos, videos, and books as well. This gave me a fantastic idea... What if my friends and loved ones could upload their media that they *legally* obtained for the enjoyment of others? What if everyone added their favourite content into the media "soup" that absorbed the flavours of whoever touched it? That would be beautiful I think, so now I am trying to make that happen!

---
{: data-content="VPN"}

For security reasons, I've decided to use a vpn to connect to the media server instead of port forwarding. It's also much easier I think. The VPN I've chosen is **tailscale** and the setup could not be simpler:

1. Download tailscale on your device and make an account. If you are not signed into the VPN network you **CANNOT STREAM OR UPLOAD ANY CONTENT**. It sounds much more annoying than it is.
2. Accept my network invite using <a href="https://login.tailscale.com/admin/invite/K67MpXH4Av5aijEq6U1B11">this</a> link. I will need to approve you after this, just let me know
3. You are connected to the VPN so now you can connect to the streaming server (next section) and upload files (next next section).

---
{: data-content="streaming"}

There are two ways to connect to the media streaming server: web and and client.

## web

**While connected to the VPN**, go to <a href="http://homelab.blowfish-yo.ts.net:8096">homelab.blowfish-yo.ts.net:8096</a>

## client

Download the jellyfin client on your streaming device (phone, computer, etc.). **While connnected to the VPN**, add a new sever with adress **homelab.blowfish-yo.ts.net:8096**

In either the website or client, you will see a login screen. If you dont see your account please contact me  so I can make you an account. I think I can automate this in the future but I don't want to.

**IMPORTANT**!!! I  will see your username and password so please **PLEASE** don't use your normal password you would use for something like your bank account. Just don't do it.

You can explore jellyfin for fun features like opensubtitles and metadata stuff. To be honsest I havent explored most of these features so let me know if you find anything cool or not cool.

---
{: data-content="uploading"}

Uploading your own media is, in my opinion, the most important yet least sexy part of this soup. Please follow these steps with care:
1. Download <a href="https://filezilla-project.org/">filezilla client</a> on your computer
2. Connect to the server with the following parameters:
  - Host = **sftp://homelab.blowfish-yo.ts.net**
  - User = ***your jellyfin username***
  - Password = ***your jellyfin password***
3. You will now be connected to the server! Please note that you are inside my  computer now so be nice and respectful. The filesystem is organised very intuitively, just navigate to the directory you want (shows, movies, music whatever) and drag your files in. It should show up soon with the correct metadata automatically.

It might be annoying to use at first but I really think this could turn into something beautiful so if this idea sounds good to you on an ideological level please give it a shot!