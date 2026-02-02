## YOINK! — We just open-sourced a free IOC extraction tool

Ever pasted a wall of text from a threat report into a notepad and started manually picking out IPs, domains, hashes, and URLs?

Yeah. We got tired of that too.

So Mike Meerkat from Datasafari.org and Claude (Anthropic) built **YOINK!** — *Your Observables Instantly Nabbed & Kategorized*.

It's a single HTML file. No install. No server. No dependencies. No internet required. Open it in your browser and start yoinking IOCs out of any text.

**What it does:**

- Extracts IPs, URLs, domains, emails, file names, MD5, SHA-1, and SHA-256 hashes
- Auto-refangs defanged indicators (hxxps, [.], (dot), [at] — you name it)
- Validates domains against the full IANA TLD list to kill false positives
- Separates file names from domains automatically
- Click any IOC to see every occurrence highlighted in the source text
- Edit, copy, delete, or reclassify any indicator on the fly
- Export to CSV, JSON, or full STIX 2.1 bundles (with TLP markings, relationships, and all the SDOs/SCOs your TIP expects)
- Dark/light theme, English/Dutch

**Who it's for:**

Threat intelligence analysts, incident responders, SOC analysts, malware researchers — anyone who deals with IOCs and is tired of doing it the hard way.

**How to use it:**

Download one file. Open it. Paste text. Hit YOINK!

That's it. Works on an air-gapped workstation, from a USB stick, or on your daily driver. ~125 KB, zero setup.

It's free, it's open source (MIT), and you can fork it and make it your own.

GitHub: [LINK TO YOUR REPO]

If you work in cybersecurity and deal with IOCs — give it a try and let us know what you think. PRs and feature ideas are welcome.

#cybersecurity #threatintelligence #ioc #opensource #infosec #dfir #incidentresponse #stix #yoink
