# adguard-home-settings

My recommendations for the ultimate AdGuard Home Configuration :)

# General settings

**Block domains using filters and hosts files** -> ✅

**Filter update interval** -> 1 hour (You can set this to 12 hours if this causes you any issues)

**Use AdGuard browsing security web service** -> ❌ (See `DNS settings` below)

**Enable log** -> ✅ (Having logs on is important for troubleshooting breakage)

**Anonymize client IP** -> ✅

**Query logs rotation** -> Custom -> 1 hour 

Make sure to select **Save**.

**Enable statistics** -> ✅

**Statistics retention** -> Custom -> 1 hour

Make sure to select **Save**.

# DNS settings

**Upstream DNS servers** ->

I would strongly recommend setting this to be [Quad9](https://www.quad9.net/) for the following reasons:

* ⭐️ Based in Switzerland 
* ⭐️ Non-profit
* ⭐️ Extremely effective at blocking malicious domains and threats right as they arise, moreso than AdGuard's protection above and most other DNS providers, see [here](https://divested.dev/misc/circumnavigator.txt) for a comparison.

Therefore, I would recommend setting this box to:

`https://dns.quad9.net/dns-query`

`tls://dns.quad9.net`

Make sure no other entries are present, so that Quad9 is actually enforced.

**Parallel requests** -> ✅

**Fallback DNS servers** -> Leave empty

**Bootstrap DNS servers** -> Remove any entries that are already present, and set this box to the following for Quad9:

`9.9.9.9`

`149.112.112.112`

`2620:fe::fe`

`2620:fe::9`

You can now select **Test upstreams** to ensure that you configured this correctly, and then don't forget to select **Apply**.

**Rate limit** -> 0

**Enable EDNS client subnet** -> ❌

**Enable DNSSEC** -> ✅

**Disable resolving of IPv6 addresses** -> ❌ (Should be default, IPv6 is important)

**Blocking mode** -> Default (Other options can cause issues)

Select **Save**.

# Encryption settings

This is out of scope for this guide, I'll probably make a separate guide dedicated just to setting this up. In the meantime, [here](https://github.com/AdguardTeam/AdGuardHome/wiki/Encryption/)'s AdGuard's documentation on this. I would recommend configuring this if possible.

(Following is under `Filters`)

# DNS blocklists

Here's where it gets fun.

Despite popular opinion, due to the reasons WaLLy3K has listed [here](https://github.com/WaLLy3K/wally3k.github.io?tab=readme-ov-file#why-use-this-over-other-sources), I think it's a good idea to use multiple lists and sources, rather than just limiting yourself to one or two giant lists. I myself constantly notice domains being blocked that were caught by only one list and missed by others. I'm not saying you should go overboard, but I do think it's a good idea to use a variety of high quality lists.

I would generally recommend using the following built-in lists:

* ⭐️ AdAway Default Blocklist *(Appears to be included, but not checked/enabled by default or listed on the selection screen here)*

**General**

* ⭐️ AdGuard DNS filter *(Enabled by default)*
* ⭐️ AdGuard DNS Popup Hosts filter
* ⭐️ AWAvenue Ads Rule
* ⭐️ Dan Pollock's List
* ⭐️ HaGeZi's Pro++ Blocklist
* ⭐️ OISD Blocklist Big
* ⭐️ Peter Lowe's Blocklist
* ⭐️ Steven Black's List

If you're fine with a little breakage, I would recommend using HaGeZi's **Ultimate** Blocklist instead of Pro++.

**Other**

* ⭐️ Dandelion Sprout's Anti Push Notifications
* ⭐️ Dandelion Sprout's Game Console Adblock List
* ⭐️ HaGeZi's Allowlist Referral (See section below, come back to this)
* ⭐️ Perflyst and Dandelion Sprout's Smart-TV Blocklist
* ⭐️ WindowsSpyBlocker - Hosts spy rules

**Security**

* ⭐️ Phishing URL Blocklist (PhishTank and OpenPhish)
* ⭐️ Dandelion Sprout's Anti-Malware List
* ⭐️ HaGeZi's Badware Hoster Blocklist
* ⭐️ HaGeZi's DynDNS Blocklist
* ⭐️ HaGeZi's The World's Most Abused TLDs (Causes rare breakage but heavily improves security)
* ⭐️ HaGeZi's Threat Intelligence Feeds
* ⭐️ NoCoin Filter List
* ⭐️ Phishing Army
* ⭐️ Scam Blocklist by DurableNapkin
* ⭐️ ShadowWhisperer's Malware List
* ⭐️ Stalkerware Indicators List
* ⭐️ The Big List of Hacked Malware Web Sites
* ⭐️ uBlock filters - Badware risks
* ⭐️ Malicious URL Blocklist (URLHaus)

**Custom lists**

I would additionally recommend adding the following lists:

* ⭐️ Admiral: `https://v.firebog.net/hosts/Admiral.txt`
* ⭐️ Ad Wars: `https://raw.githubusercontent.com/jdlingyu/ad-wars/master/hosts`
* ⭐️ anudeepND's Blacklist: `https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt`
* ⭐️ Blocklist Project - Ads: `https://blocklistproject.github.io/Lists/alt-version/ads-nl.txt`
* ⭐️ Blocklist Project - Crypto: `https://blocklistproject.github.io/Lists/alt-version/crypto-nl.txt`
* ⭐️ Blocklist Project - Fraud: `https://blocklistproject.github.io/Lists/alt-version/fraud-nl.txt`
* ⭐️ Blocklist Project - Malware: `https://blocklistproject.github.io/Lists/alt-version/malware-nl.txt`
* ⭐️ Blocklist Project - Phishing: `https://blocklistproject.github.io/Lists/alt-version/phishing-nl.txt`
* ⭐️ CAMELEON: `https://sysctl.org/cameleon/hosts`
* ⭐️ CoinBlocker: `https://zerodot1.gitlab.io/CoinBlockerLists/hosts_browser`
* ⭐️ DeveloperDan Ads & Tracking: `https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt`
* ⭐️ Digital Side Threat Intel: `https://osint.digitalside.it/Threat-Intel/lists/latestdomains.txt`
* ⭐️ Divested Combined Blocklist: `https://divested.dev/hosts-domains-wildcards`
* ⭐️ EasyList: `https://v.firebog.net/hosts/Easylist.txt`
* ⭐️ EasyPrivacy: `https://v.firebog.net/hosts/Easyprivacy.txt`
* ⭐️ Feudo Tracker Abuse: `https://feodotracker.abuse.ch/downloads/ipblocklist.txt`
* ⭐️ FrogEye First Party Trackers: `https://hostfiles.frogeye.fr/firstparty-trackers-hosts.txt`
* ⭐️ HaGeZi's Encrypted DNS Servers: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/doh.txt`
* ⭐️ HaGeZi/xRuffKez's Newly Registered Domains (14 days): `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/nrds.10.txt`
* ⭐️ HaGeZi's Threat Intelligence Feeds - IPs: `https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/tif-ips.txt`
* ⭐️ hBlock: `https://hblock.molinero.dev/hosts_adblock.txt`
* ⭐️ hostsVN: `https://raw.githubusercontent.com/bigdargon/hostsVN/master/hosts`
* ⭐️ KADhosts: `https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt`
* ⭐️ Magnesium1062's Apple Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/apple.txt`
* ⭐️ Magnesium1062's Brave Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/brave.txt`
* ⭐️ Magnesium1062's Data Brokers Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/data-brokers.txt`
* ⭐️ Magnesium1062's Google Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/google.txt`
* ⭐️ Magnesium1062's Microsoft Blocklist: https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/microsoft.txt
* ⭐️ Magnesium1062's Mozilla Blocklist: https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/mozilla.txt
* ⭐️ Magnesium1062's Mozilla Blocklist (IPs): https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/mozilla-ips.txt
* ⭐️ Magnesium1062's Roblox Blocklist: https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/roblox.txt
* ⭐️ Magnesium1062's Stalkerware Blocklist: https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/stalkerware.txt
* ⭐️ Maltrail Malware Domains: `https://raw.githubusercontent.com/stamparm/aux/master/maltrail-malware-domains.txt`
* ⭐️ NSA Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/nsablocklist/hosts`
* ⭐️ Prigent-Ads: `https://v.firebog.net/hosts/Prigent-Ads.txt`
* ⭐️ Prigent-Crypto `https://v.firebog.net/hosts/Prigent-Crypto.txt`
* ⭐️ Prigent-Malware: `https://v.firebog.net/hosts/Prigent-Malware.txt`
* ⭐️ Quidsup NoTrack Malware Blocklist: `https://gitlab.com/quidsup/notrack-blocklists/raw/master/notrack-malware.txt`
* ⭐️ Quidsup NoTrack Tracker Blocklist: `https://gitlab.com/quidsup/notrack-blocklists/raw/master/notrack-blocklist.txt`
* ⭐️ RPiList-Malware: `https://v.firebog.net/hosts/RPiList-Malware.txt`
* ⭐️ RPiList-Phishing: `https://v.firebog.net/hosts/RPiList-Phishing.txt`
* ⭐️ Spam404: `https://raw.githubusercontent.com/Spam404/lists/master/adblock-list.txt`
* ⭐️ Ut1 Cryptojacking Domains: `https://raw.githubusercontent.com/olbat/ut1-blacklists/master/blacklists/cryptojacking/domains`
* ⭐️ Ut1 Malware Domains: `https://raw.githubusercontent.com/olbat/ut1-blacklists/master/blacklists/malware/domains`
* ⭐️ Ut1 Phishing Domains: `https://raw.githubusercontent.com/olbat/ut1-blacklists/master/blacklists/phishing/domains`
* ⭐️ WaLLy3K's Personal Blocklist: `https://v.firebog.net/hosts/static/w3kbl.txt`

Additionally, if you're fine with a little breakage, I would highly recommend:

* ⭐️ 1Hosts (Pro): `https://o0.pages.dev/Pro/adblock.txt`
* ⭐️ HaGeZi's Encrypted DNS Servers - IPs: `https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/doh-ips.txt`

It might seem like a lot, but these are carefully picked high quality lists with strong coverage, and it doesn't really hurt to use multiple like this.

You could also consider, depending on your preference:

* ⭐️ DeveloperDan's AMP Blocklist: `https://www.github.developerdan.com/hosts/lists/amp-hosts-extended.txt` - Blocks [AMP](https://brave.com/privacy-updates/18-de-amp/#why-is-amp-harmful) websites
* ⭐️ Magnesium1062's DRM Blocklist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/drm.txt` - Blocks websites associated with [DRM](https://www.eff.org/deeplinks/2017/10/drms-dead-canary-how-we-just-lost-web-what-we-learned-it-and-what-we-need-do-next) technology/its provisioning 

# DNS allowlists

I would recommending adding the following here:

* ⭐️ Magnesium1062's Whitelist: `https://codeberg.org/Magnesium1062/blocklists/raw/branch/main/whitelist.txt`
* ⭐️ HaGeZi's URL Shorteners: `https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/whitelist-urlshortener.txt`

# Blocked services

You should add in here any services you don't use or care about. For instance, I usually block `Facebook`, `Instagram`, `LinkedIn`, `TikTok`, & `WhatsApp`, as I don't use or care about any Facebook, LinkedIn, or TikTok services, and I don't want to connect to or be tracked by them.

# Custom filtering rules 

While being nice from a usability perspective, HaGeZi's Referral Allowlist and the AdGuard DNS filter list do allow some questionable ad/tracking domains we don't want unblocked. I would recommend adding the following to your filtering rules:

`||adservice.google.*^$important`

`||adsterra.com^$important`

`||amplitude.com^$important`

`||analytics.edgekey.net^$important`

`||analytics.twitter.com^$important`

`||app.adjust.*^$important`

`||app.*.adjust.com^$important`

`||app.appsflyer.com^$important`

`||doubleclick.net^$important`

`||googleadservices.com^$important`

`||guce.advertising.com^$important`

`||metric.gstatic.com^$important`

`||mmstat.com^$important`

`||statcounter.com^$important`

Now select **Apply**.

# Additional recommendations

* Use a privacy-respecting browser like [Firefox](https://www.mozilla.org/firefox/).

* Use a content blocking extension like [uBlock Origin](https://github.com/gorhill/uBlock).

* Enable Safe Browsing in your browser if possible and if it's not done in a privacy-invasive way. (You should use i.e. [Google Safe Browsing on "Standard" Mode](https://safebrowsing.google.com/), [Firefox's Safe Browsing](https://support.mozilla.org/kb/how-does-phishing-and-malware-protection-work), [Brave's Safe Browsing](https://brave.com/privacy/browser/#safe-browsing), & [Safari's Fraudulent Website Warning](https://www.apple.com/legal/privacy/data/en/safari/), you should avoid most other options i.e. [Google Safe Browsing on "Enhanced" Mode](https://safebrowsing.google.com/), [Microsoft SmartScreen](https://learn.microsoft.com/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-smartscreen/), & [Opera Sitecheck](https://blogs.opera.com/security/2021/01/making-browsing-safe-from-phishing/)).

* Use a (reputable) anti-virus if possible. On Windows, you can use the built-in [Microsoft Defender Antivirus](https://en.wikipedia.org/wiki/Microsoft_Defender_Antivirus), on macOS, you can stick to the built-in [XProtect](https://support.apple.com/guide/security/protecting-against-malware-sec469d47bd8/web), on Android, you can use [Hypatia](https://f-droid.org/packages/us.spotco.malwarescanner/), and on Linux, you can use [ClamAV](https://www.clamav.net/). NOTE: You should install Hypatia through the [DivestOS Official Repo](https://divestos.org/fdroid/official/?fingerprint=E4BE8D6ABFA4D9D4FEEF03CDDA7FF62A73FD64B75566F6DD4E5E577550BE8467) instead of F-Droid's main repo, as it will allow you to receive quicker updates directly from the developer. It's also recommended to use [F-Droid Basic](https://f-droid.org/en/packages/org.fdroid.basic/) as your F-Droid client of choice.