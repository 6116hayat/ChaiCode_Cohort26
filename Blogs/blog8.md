![CoverImage](./BlogResources/Blog8Cover.jpg)

<div align="center">
<h1>TCP vs UDP: When to Use What, and How TCP Relates to HTTP</h1>
</div>

[Blog link](https://dev.to/6116hayat/tcp-vs-udp-when-to-use-what-and-how-tcp-relates-to-http-577)

---

## 🎙️ Introduction

Hey Reader — welcome back

Okay, that _did_ sound like an NPC. Let’s fix that.

In last blog, we really had an intense discussions about the internet rules.

If you’ve been following along, you should already have a rough mental map of:

- how devices connect,
- how DNS finds servers,
- and how TCP and UDP choose _how_ data moves.

If not, quick catch-up here:

Blog 1: [Understanding Network Devices - DEV Community](https://dev.to/6116hayat/understanding-network-devices-3gg1)

Blog 2: [How DNS Resolution Works - DEV Community](https://dev.to/6116hayat/how-dns-resolution-works-24i9)

Blog 3: [DNS Record Types Explained - DEV Community](https://dev.to/6116hayat/dns-record-types-explained-2m7g)

Blog 4: [TCP vs UDP: When to Use What, and How TCP Relates to HTTP - DEV Community](https://dev.to/6116hayat/tcp-vs-udp-when-to-use-what-and-how-tcp-relates-to-http-1h6c)

The more I learn about this stuff, the more I understand why the internet is considered one of humanity’s greatest inventions.
Sometimes it honestly feels like I’m debugging packets with Iron Man holograms floating around me.

Anyway — before I drift again — let’s talk TCP.

---

## 🧨 When Data has no Rules

### 🤔 Internet with & without rules

Imagine a highway.

No traffic lights.

No lanes.

No signs.

Just vibes.

Every car rushes forward trying to win. Very GTA energy. Fun for chaos — terrible for reaching a destination.

That’s what the internet looks like _without rules_.

On the internet, cars are **data packets**.

And the “rules” are called **protocols**.

With protocols:

- Data arrives reliably
- Packets stay in order
- No duplication
- Errors are detected and corrected

Without protocols:

- Packets get lost
- Order breaks
- Duplicates appear
- Corrupted data slips through

Chaos. Every time.

---

### 🚫 Why Internet cannot rely on “best effort” alone

The internet’s core design is **best effort delivery**.

That means:

- The network _tries_ to deliver packets
- But it makes **zero promises**

If a packet is lost, delayed, duplicated, or reordered — the network shrugs and moves on.

That’s fine for:

- video streaming
- voice calls
- casual browsing

But it’s disastrous for:

- file downloads
- emails
- online payments

When correctness matters, _best effort isn’t enough_.

That’s where **TCP** enters.

---

## 📌 TCP and 3-way handshake

![Handshake](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sanq7dpnhv0vbfkgtc0k.png)

As we have seen TCP in the last blog and discussed its meaning and full-form and where to use TCP , I won’t be able to repeat myself.

Don’t worry I will explain TCP here but in short…

You are always welcomed to checkout the last blog as well the series

### 🌐 TCP: Reliable Connections

TCP (Transmission Control Protocol) sits at the **transport layer** and is the backbone of reliable internet communication.

Key traits:

- Connection-oriented
- Reliable delivery
- Ordered data transfer
- No duplication

TCP doesn’t just send data.

It **builds trust first**.

---

### 🤝 Why a handshake is Needed

Before sending data, TCP asks one simple question:

> “Are you there — and are you ready?”

The handshake:

- Confirms both sides are reachable
- Synchronizes sequence numbers
- Establishes reliability rules

Only after this agreement does data flow.

---

### 🔄️ TCP 3-Way Handshake

The TCP 3-way handshake establishes a reliable connection before data transfer begins.

**The three steps:**

1. **SYN**

   Client: “I want to connect. Here’s my starting sequence number.”

2. **SYN-ACK**

   Server: “I hear you. Here’s mine — and I acknowledge yours.”

3. **ACK**

   Client: “Acknowledged. Let’s begin.”

After this, the connection is live.

**Why three steps?**

- Both sides confirm readiness
- Both sides acknowledge each other
- No assumptions, no guessing

That’s reliability by design.

- This guarantees both devices are fully ready and “in sync”

---

### 🗣️ Conversation Analogy:

- Client: “Hey, can we talk? My first word will be number 100.” (SYN)
- Server: “Sure! I heard you. My first word will be number 300.” (SYN-ACK)
- Client: “Got it, I’ll listen starting at 300.” (ACK)

---

## 📦 Reliable Data Transfer and Connection Closure:

### Data Transfer After Handshake

- Once the handshake is established, data flows in segments
- Each segments has a unique number known as sequence number, receiver acknowledges receipt.

### Role of Sequence Numbers and Ack’s

![Sequence](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bodwz4yexyvcgojg0sa5.png)

- Sequence number ensure data arrives in order
- Acks confirms successful delivery
- If an ACK is missing, the sender knows something is wrong

### Detecting Packet Loss & prevention

![Detection_Loss](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5zd8dpsigjad7v38h0fq.png)

- TCP uses timeouts and duplicates ACK’s to detect lost packets
- If a packet is lost, TCP retransmits it to maintain reliability

### Ensuring Correctness

- TCP checks data integrity using **checksums**.
- If corrupted data is detected, it is discarded and retransmitted.

---

## 😁 Ending Thought

I’m trying my best to stay consistent with this series, but time management is starting to hit hard.
So for the next few blogs, the long introductions and ending thoughts might take a back seat.

The focus will stay the same though:
understanding how the internet actually works — clearly, honestly, and without magic.

Humor may go quiet for a bit, but the learning won’t.
