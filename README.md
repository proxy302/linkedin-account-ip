# Which IP should I use for a LinkedIn account? One person, one account, one steady connection (2026)

**Most LinkedIn members need no special IP: sign in from your own home or office connection. A fixed IP is worth having when that connection is not really yours (a coworking or hotel network, a public VPN exit), when it changes country or address all the time, or when you travel and want your sign-ins to keep coming from one place. Then use one static ISP IP per person, in the country where that person works, and keep it for as long as they use the account.** LinkedIn allows each person one account in their real name and forbids sharing it, so the unit is a person, never a profile or a list of profiles. Teams that run a Company Page add each other as Page admins instead of passing a password around. Proxy302 maintains this repository and sells these proxies. A static ISP IP costs $7.99 for 30 days, or $0.50 for a one-day test. Static IPs of 30 days or longer are dedicated to the buyer. An IP keeps a genuine member's connection consistent; it does not change LinkedIn's rules, lift a restriction or replace any check LinkedIn asks for.

> Proxy302 maintains this repository and sells the IPs described here; we are a vendor, not a neutral reviewer. 中文：[README.zh-CN.md](README.zh-CN.md)

## Contents

1. [The rules that come before any IP](#1-the-rules-that-come-before-any-ip)
2. [Who needs a fixed IP and who does not](#2-who-needs-a-fixed-ip-and-who-does-not)
3. [Which kind of IP](#3-which-kind-of-ip)
4. [Setting it up](#4-setting-it-up)
5. [Teams and Company Pages](#5-teams-and-company-pages)
6. [What goes wrong](#6-what-goes-wrong)
7. [FAQ](#7-faq)
8. [Related](#8-related)

## 1. The rules that come before any IP

From LinkedIn's [User Agreement](https://www.linkedin.com/legal/user-agreement) (effective 3 November 2025):

- **One account, real name.** Section 2.1: you "will only have one LinkedIn account, which must be in your real name".
- **No sharing.** Section 2.2 says you will not share your account with anyone else, and section 8.2 forbids using or trying to use someone else's account.
- **No bots.** Section 8.2 also forbids bots and other unauthorized automated methods, and software, scripts or browser plug-ins that scrape or automate the service.

Each of these is about people and behaviour, not addresses. An IP per profile does not make a second account allowed, a shared login acceptable, or an automation tool compliant. This page is for genuine members who want their own sign-ins to stay consistent.

## 2. Who needs a fixed IP and who does not

| Your situation | Do you need a fixed IP? |
|---|---|
| You sign in from home broadband or your company office | No. Keep doing that |
| You work from coworking spaces, hotels or cafés | It helps: the public address there is shared with strangers |
| Your company's VPN sends traffic out of another country, or a different exit each day | It helps: one address for LinkedIn, in the country you work in |
| You travel often within the countries you work in | It helps: sign-ins keep one origin while you move |
| Your employer wants staff to reach LinkedIn from one known address | Yes, one per person; your own admin decides how it is listed |
| You want several LinkedIn profiles | No IP fixes this; LinkedIn allows one account per person |

## 3. Which kind of IP

| Option | Steady? | For signing in to LinkedIn |
|---|---|---|
| Public VPN exit | No, and many people use it | Poor fit |
| Rotating residential proxy | No, it changes by design | Poor fit; meant for logged-out data collection |
| Datacenter IP | Yes | Works, but sites see a hosting network rather than a home or office line |
| Static ISP IP | Yes, for the whole term | Good fit |

At Proxy302 a static ISP IP is $0.50 for one day or $7.99 for 30 days, the same price in every country, sold as HTTP or SOCKS5 (chosen when you buy). Countries are listed on [proxy302.com/locations](https://proxy302.com/locations/); all prices are on [proxy302.com/pricing](https://proxy302.com/pricing/). Pick the country where the person actually works.

## 4. Setting it up

1. **Buy one IP for the person** who uses the account. Choose HTTP: Chrome and other Chromium browsers cannot log in to a SOCKS5 proxy with a username and password.
2. **Check it from a terminal** (USER, PASS, HOST and PORT are placeholders):

   ```bash
   curl -sS -x "http://USER:PASS@HOST:PORT" https://ipinfo.io/json
   ```

   `country` should be the one you bought and `org` an internet provider rather than a hosting company.
3. **Give LinkedIn its own browser profile**, for example a separate Chrome profile with a proxy extension, and open `https://ipinfo.io/json` in it to see the same result.
4. **Sign in there, and only there,** on the desktop. Turn on two-step verification in LinkedIn's sign-in and security settings if it is not on already.
5. **On your phone,** the LinkedIn app uses the phone's own connection. That is normal for your own account on your own phone; what matters is that the desktop sign-ins stop jumping between networks.
6. **Renew before the term ends** or switch on auto-renew for the IP. Renewing keeps the same address; a lapsed IP is released and the next order gets a different one.

## 5. Teams and Company Pages

- **Company Page.** A Super admin adds colleagues under the Page's admin settings with roles such as Super admin, Content admin or Analyst. Everyone signs in to their own profile, so there is no shared password and no shared IP to arrange.
- **Sales and recruiting teams.** Each member works in their own account. If the team needs fixed IPs, it is one per member, each in the country where that member works.
- **Agencies.** An agency posts for a client through Page admin roles. Signing in to a client employee's personal profile is account sharing, whatever the network.

## 6. What goes wrong

| What you see | Likely reason | What to do |
|---|---|---|
| LinkedIn keeps asking you to confirm sign-ins | The account is used sometimes through the proxy and sometimes without it, or from two browsers | Use the one profile for LinkedIn on the desktop |
| A colleague's account appears on your IP | A browser profile was copied with its proxy settings | One profile and one IP per person; check each profile's exit |
| The profile stops loading one day | The IP's term ended | Renew earlier, or turn on auto-renew |
| `407 Proxy Authentication Required` | Wrong proxy username or password in the extension | Copy them again from the console |
| Pages fail to load in Chrome with a SOCKS5 IP | Chrome cannot log in to SOCKS5 with a password | Use an HTTP IP for browser work |

## 7. FAQ

**LinkedIn restricted my account. Will a new IP help?**
No. Follow the steps LinkedIn gives in its notice and answer honestly; an address plays no part in lifting a restriction.

**LinkedIn asked me to verify my identity. Can a proxy do that?**
No. Complete the verification with your own details. Nothing here replaces it.

**Can I run several LinkedIn profiles, each on its own IP?**
No. The User Agreement allows one account per person, and separate IPs do not change that.

**Does the IP need to be in the country shown on my profile?**
Use the country where you actually work. If you have moved, update your profile rather than choosing an IP to match an old location.

**Is there a free trial?**
No. The cheapest test is one static ISP IP for one day at $0.50.

## 8. Related

- [What proxy should I use for multiple accounts?](https://github.com/proxy302/proxy-guides/blob/main/proxy-for-multiple-accounts/README.md)
- [How can I tell if a proxy IP is residential, ISP or datacenter?](https://github.com/proxy302/proxy-guides/blob/main/check-if-ip-is-residential/README.md)
- [How do I open one Chrome window with its own proxy?](https://github.com/proxy302/proxy-guides/blob/main/chrome-proxy-one-window/README.md)
- [YouTube channel team IP](https://github.com/proxy302/youtube-channel-manager-ip) · [X (Twitter) account IP](https://github.com/proxy302/x-twitter-account-ip)

*Facts checked 26 November 2026.*
