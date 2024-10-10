+++
title = "DD-WRT Saves In-Laws From WRT160N Poisonous Cache!"
date = "2010-09-25"
[taxonomies]
tags = ["router", "security"]
+++

Usually, when I buy any gadget of note, I research _heavily_ on the Internet before buying. Product research tends to serve me well, but occasionally I bog down into paralysis of analysis.

We spent the last week or so visiting out-of-state with our families. My in-laws networking had fallen into a rather sad state, so I figured I’d fix them up. I decided to violate my M.O. and buy a router on the spot from a brick and mortar store as I figured any of the routers ought to be serviceable enough for their needs. Linksys products had served me well in the past, so I simply grabbed this shiny looking router and headed back to their house:

<img src="/images/linksys-wrt160nv3.png" alt="Linksys WRT160Nv3 router" style="display: block; margin-left: auto; margin-right: auto;">

Big. Mistake.

The [WRT160N line](http://en.wikipedia.org/wiki/Linksys_routers#WRT160N) (as well as the WRT310N line apparently) is plagued with a nasty vulnerability that Cisco is not addressing in a forthright manner. Apparently, the WRTN160N series has been deprecated for a (inferior) similar product line (Linksys E1000). I can now see at least one good reason they are burying it.

The problem manifested itself as an occasional redirect when browsing. I noticed it after “google.com” pulled up Pricegrabber. Many people first see the issue via a facebook.com to myspace.com redirect. The problem is OS/browser agnostic because it seems to be some sort of DNS cache poisoning in the router firmware (or a horrible bug if you believe it is an accident).

It’s weird freaky stuff as well as an enormous security hole. Personally, I think someone slipped intentionally malicious code in somehow as the redirects seem to be targeted: google to pricegrabber, facebook to myspace, liberal news site to conservative news site.

There is an easy workaround. TAKE IT BACK FOR A REFUND! If you own this device and you can return it, I absolutely urge you to do so. Cisco has stonewalled for over a year and the device is flawed. Unfortunately, we couldn’t return it as I realized the extent of the problem on day 33 after purchase.

There is another relatively simple workaround. You can manually set the DNS settings on every machine on the network to bypass the router and utilize your ISP, OpenDNS, or Google’s DNS servers instead. I didn’t like this as it means you need to change settings back to automatic if you leave the network. Conversely, visitors would need to manually configure DNS when on the network.

I decided to entirely replace the offending stock firmware by flashing [DD-WRT](http://www.dd-wrt.com/) onto the device. This turned out beautifully. The firmware flashed on exactly as hoped, held up stably under testing, and resolved the problem. Directions for flashing DD-WRT onto the WRT160Nv3 can be found [here](http://www.dd-wrt.com/wiki/index.php/Linksys_WRT150N_%26_WRT160N#WRT160Nv3_Instructions).

As of this post date, I do recommend the build suggested (`dd-wrt.v24-13575_NEWD-2_K2.6_mini_wrt160nv3.bin`) as it seems to work perfectly.