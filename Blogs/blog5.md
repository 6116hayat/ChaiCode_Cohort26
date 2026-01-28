![CoverImage](./BlogResources/Blog5Cover.jpg)

<div align="center">
<h1>How DNS Resolution Works:</h1>
</div>

[Blog Link](https://dev.to/6116hayat/how-dns-resolution-works-24i9)

---

## 🎙️ Introduction

Hello reader — welcome back

If you’ve been following this series, first of all: respect. Consistency is hard, and I’m trying (temporarily successful so far).

If not, and you are new here — this is my **second blog in the networking series**, where I mostly _blabber about my learnings_ of networking so developers can seek knowledge along the way.

(It’s good I’m being consistent temporarily.)

My last blog was about **Networking Devices** — I talked about routers, switches, firewalls — and how they work together silently to make our lives less chaotic.

You can check it out here — [[Networking Devices](https://dev.to/6116hayat/understanding-network-devices-3gg1)]

This blog will be consists of:

- How the internet actually works behind the scenes
- The workers of internet — the logbook for websites
- the chain behind all website lookups, hopping from server to server
- and how easy it looks, but how not easy it actually is

I hope this blog gives you a sense of **logic behind how things work**, and makes the internet feel **predictable, not magical**.

---

## 🌐 DNS: The Name-to-Number Translator

Let’s try to decode DNS using What, How and Why?

![DNS](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9mfmi51j1lok80un7buf.png)

---

### 1️⃣ What?

> What is DNS?
> DNS (Domain Name System) converts human-friendly domain names into IP addresses so browsers can load websites.

Computers don’t understand names.

They understand numbers.

But memorizing

When you type **google.com**, your system eventually needs something like: `142.250.190.14`

A modern analogy (not the phonebook one)

Everyone uses the phonebook analogy — let’s be modern

DNS is like the search bar in Netflix or Spotify.

When you type “Stranger Things” on Netflix, you don’t need to know:

- which server stores it
- where it lives physically
- or what the internal file path is

You just type the name — and Netflix figures out the rest.

DNS does the same thing for internet.

---

### 2️⃣ How?

The whole working of DNS works between IP (device address as numbers) and actual website names.

1. You type a domain name into your browser
2. Browser checks cache (local memory) to see if it already knows the IP
3. DNS Resolver (usually your ISP or a public resolver like Google DNS) starts the lookup
4. Root Servers direct the resolver to the right Top-Level Domain (e.g., `.com` , `.net` , `.org` ).
5. TLD Servers point to the authoritative server for that domain.
6. Authoritative Server gives the final IP address.
7. Browser connects to the IP and loads the site.

(We’ll break down each part of DNS — no rush.)

---

### 3️⃣ Why?

Q. Why name resolution exists?

(Humans prefer names, while computers need numbers)

- Humans like names: It’s easier to remember google.com than 142.250.190.14
- Computers need IP addresses:
  Every device on the internet has a unique numerical identity
- DNS bridges the gap
  It translates human-friendly names into machine-friendly IPs

⇒ Key Takeaways:.

1. User-friendly → no IP memorization
2. Scalable → handles billions of queries daily
3. Efficient → caching reduces load and speeds things up
4. Foundational → without DNS, the internet breaks instantly

---

## 🔎 `dig` : Your X-Ray Tools for DNS

Being a developer myself, let me hand you a tool that removes the illusion.

The internet looks neat and polished —
behind the scenes, it’s organized chaos. DNS included.

Browsers quietly resolve DNS in the background and never show the details.

Engineers, however, need visibility.

That’s where dig comes in.

---

### What is `dig` ?

> dig (Domain Information Groper) is a command line tool used to query DNS servers directly.

Honestly, the explanation hides in the name itself — it **digs**.

---

### What `dig` shows us

Browser hides DNS from you. They quietly resolve name in background, never showing the messy details. Engineers, however, need visibility — and that’s where dig comes in.

![Dig_Sectinons](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nqcz02wgen0ytu7qf5x7.png)

A typical `dig` output has three important sections:

1️⃣ **Question Section**

- Shows what you asked DNS
- Domain name + record type

2️⃣ **Answer Section**

- The actual DNS records returned
- IP addresses, CNAMEs, MX records, etc.

3️⃣ **Authority Section**

- Lists the authoritative name servers
- Tells you who owns the truth for this domain

`dig` doesn’t make DNS faster.

It makes DNS **visible**.

Let’s start asking DNS:

**Who knows what?**

---

## ⛓️ The DNS chain of Responsibility

We casually say “DNS gives IP addresses”, but internally it’s a **chain of responsibility** — a sequence of back-and-forth lookups.

No single server knows everything.

DNS is intentionally built as a **layered hierarchy**.

![DNS_Flow](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kksdsmfmxrrb3ct40qlz.png)

---

### 🌍 Root Name Servers

- Represented by the dot (`.`)
- They don’t know domain IPs
- They know where TLD servers live

---

### 🌐 TLD Servers

- Examples: `.com`, `.org`, `.net`
- They delegate responsibility further
- They point to authoritative name servers

---

### 🏛️ Authoritative Servers

- Hold actual DNS records (A, AAAA, MX, CNAME)
- Final source of truth for a domain

---

### 🔄 Recursive Resolvers

- Work on behalf of users (your browser / OS)
- Start at root → TLD → authoritative
- Cache results for performance

Your laptop never talks to root servers directly.

Resolvers do the heavy lifting.

In short:

```mathematica
Root → TLD → Authoritative Server → Resolver
```

### Bonus: What is an NS record?

- NS (Name Server) records specify which servers are responsible for a domain
- They answer one question:

> “Who should I ask next for the real DNS information?”

![NS_Record](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1fb4r79teyyfjghlq6bn.png)

---

## 🧭 How a simple Domain Lookup Really Works

Now let’s bring dig back — and map it to the real DNS flow.

1️⃣ **Root servers**

```bash
dig . NS
```

2️⃣ **TLD servers**

```bash
dig com NS
```

3️⃣ **Authoritative servers**

```bash
dig google.com NS
```

(Returns name servers, not IPs)

4️⃣ **Final IP**

```bash
dig google.com
```

Caching makes this fast.

Once a resolver learns the answer, it remembers it — that’s why you don’t query root servers every time you open Google.

---

## 💡Ending Thought

So here we are —

- from names to numbers,
- through servers and responsibility chains,
- seeing DNS for what it really is:

All of this happens in milliseconds.

Even Flash would feel some competition.

Next time a website loads slowly, remember —
DNS might be throwing tantrums.

In future blogs, we’ll talk about DNS records, caching, and failures.

DNS is invisible —
but nothing on the internet works without it.

---
