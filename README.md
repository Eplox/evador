# IPS / IDS download evasion

## Background
I was hired by a customer to run a malware phishing campaign, but had to improvise after a recon which uncovered:
- The customer email spam server was link-crawling
- The customer has IPS (Intrusion Prevention Firewall) with SSL inspection enabled
- IPS is able to unpack / decode multiple levels of compressions
- IPS has both signature detection and sandboxing functionality
- IPS is also blocking known bad file extensions, such as bat, dll, jar, hlp, lnk, e.g.

This prevented me from doing any attachment-based or standard download related phishing, so had to think outside the box.
Solution was a JavaScript downloader, which first grabbed an encoded payload and loaded it into the DOM, then decoded it and saved the file locally on the victim's computer.

Proof of Concept can be tested here http://hisec.no/evador.html
