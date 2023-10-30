<!-- .slide: data-auto-animate data-auto-animate-id="patat" -->

## Master Thesis

Frank Nijeboer

<span data-id="protocol">A</span>
<span data-id="p">P</span><span data-id="protocol">rotocol for</span>
<span data-id="at">AT</span><span data-id="protocol">testation in</span>
<span data-id="a">A</span><span data-id="protocol">rm</span>
<span data-id="t">T</span><span data-id="protocol">rustZone</span>

Note:
- My name
- I'll be taking you on a trip through the Arm TrustZone and most notably Attestation
- Because I'm working on a Protocol

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="patat" data-auto-animate-easing="cubic-bezier(0.770, 0.000, 0.175, 1.000)" data-auto-animate-duration="1.2" -->

<span data-id="protocol" data-auto-animate-delay="0" style="display-inline-block; font-size: 0px">A</span>
<span data-id="p" data-auto-animate-delay="0" style="display-inline-block; color: #224099; font-size: 120px;">P</span><span data-id="protocol" data-auto-animate-delay="0.1" style="display-inline-block; font-size: 0px">rotocol for</span>
<span data-id="at" data-auto-animate-delay="0.1" style="display-inline-block; color: #224099; font-size: 120px;">AT</span><span data-id="protocol" data-auto-animate-delay="0.2" style="display-inline-block; font-size: 0px">testation in</span>
<span data-id="a" data-auto-animate-delay="0.2" style="display-inline-block; color: #224099; font-size: 120px;">A</span><span data-id="protocol" data-auto-animate-delay="0.3" style="display-inline-block; font-size: 0px">rm</span>
<span data-id="t" data-auto-animate-delay="0.3" style="display-inline-block; color: #224099; font-size: 120px;">T</span><span data-id="protocol" data-auto-animate-delay="0.4" style="display-inline-block; font-size: 0px">rustZone</span>

---

<!-- .slide: data-auto-animate data-auto-animate-id="" -->

## How do you make PATAT?

<img class="r-stretch" src="./dist/img/max-patat.png" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="" -->

<img class="r-stretch" src="./dist/img/max-patat.png" />

1. Cut potatoes <!-- .element: class="fragment fade-in"-->
2. Fry them <!-- .element: class="fragment fade-in"-->
3. Serve them <!-- .element: class="fragment fade-in"-->

Note:
And I hear you thinking, nice joke. But, we will come back to patat shortly.

---

# Cyber Security

Note:
The world is burning if we look at the news sometimes

vvv

<!-- .slide: data-background-iframe="https://www.cybertalk.org/2023/01/19/top-10-cyber-security-threats-in-2023/" data-background-interactive -->

vvv

<!-- .slide: data-background-iframe="https://techhq.com/2021/08/heres-how-hackers-exploit-iot-device-vulnerabilities-to-invade-hardware/" -->

vvv

<!-- .slide: data-background-iframe="https://www.helpnetsecurity.com/2023/10/16/iot-security-strategy/" -->

Note:
So what can we do to make software more secure?

vvv

<!-- .slide: data-auto-animate -->

## Compartmentalization

Split up your code

vvv

<!-- .slide: data-auto-animate -->

## Compartmentalization

<img class="r-stretch" src="https://fromscratchfast.com/wp-content/uploads/2020/06/Baked-French-Fries-Recipe-2.jpg" />

Note:
- One large potato -> everything
- This piece handle private information
- Just splitting up is not secure. We need something more

vvv


<!-- .slide: data-auto-animate -->

### <span data-id="towards">How to get better </span><span data-id="hardware-based" style="font-size: 0;">Hardware-based </span><span data-id="security">security</span><span data-id="question-mark">?</span>

vvv

<!-- .slide: data-auto-animate -->

### <span data-id="towards" style="font-size: 0;">Can we improve </span><span data-id="hardware-based">Hardware-based </span><span data-id="security">security</span><span data-id="question-mark" style="font-size: 0;">?</span>

Note:
We can try with hardware based security

vvv

<!-- .slide: data-transition="zoom-out" -->

<h3 class="fragment fade-in-then-semi-out" data-fragment-index="1">Intel SGX</h3>
<h3 class="fragment fade-in-then-semi-out" data-fragment-index="2">RISC-V MultiZone</h3>

<div class="r-stack">
<img src="./dist/img/sgx.png" class="fragment fade-in-then-out" height="200" data-fragment-index="1" />
<img src="./dist/img/multizone.png" class="fragment fade-in-then-out" height="200" data-fragment-index="2" />
<img src="./dist/img/Arm-TrustZone-Logo-2337384223.png" class="fragment fade-in-then-out" height="200" data-fragment-index="3" />
</div>

Note:
- Most hardware designers nowadays have some form of it.
- These are some examples. In our case, we are, obviously interested in TrustZone.

vvv

<!-- .slide: data-auto-animate data-transition="zoom-in" -->

## TrustZone

Since 2004

Normal World 🖥️  <!-- .element: class="fragment fade-in"-->

Secure World 🔒 <!-- .element: class="fragment fade-in"-->

Note:
- Centers around the idea that there are two domains in the computer that must be isolated from each other


vvv

<!-- .slide: data-auto-animate -->

<div style="float: left; width: 50%;">
<img src="dist/img/trustzone_layout.png"/>
</div>

<div style="float: left; width: 50%;">
<h2>TrustZone</h2>
<p class="fragment fade-in">NS Bit</p>
<p class="fragment fade-in">Exception Levels</p>
<p class="fragment fade-in">Secure Monitor Call</p>
</div>
</div>

Note:
- On the left, normal, right secure world
- Only one at a time
- As you may know, Arm systems use Exception Levels. So higher has control over lower
- But, now we want to have part of our app "invisible" to the Rich OS

---

<!-- .slide: data-auto-animate data-auto-animate-id="tee" -->

<span data-id="t" data-auto-animate-delay="0" style="display-inline-block; color: #224099; font-size: 120px;">T</span><span data-id="tee" data-auto-animate-delay="0.1" style="display-inline-block; font-size: 0px">rusted</span>
<span data-id="e" data-auto-animate-delay="0.1" style="display-inline-block; color: #224099; font-size: 120px;">E</span><span data-id="tee" data-auto-animate-delay="0.2" style="display-inline-block; font-size: 0px">xecution</span>
<span data-id="e2" data-auto-animate-delay="0.2" style="display-inline-block; color: #224099; font-size: 120px;">E</span><span data-id="tee" data-auto-animate-delay="0.3" style="display-inline-block; font-size: 0px">nvironment</span>

Note:
- TrustZone enables this thing called a TEE

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="tee" data-auto-animate-easing="cubic-bezier(0.770, 0.000, 0.175, 1.000)" data-auto-animate-duration="1.2" -->

<span data-id="t">T</span><span data-id="tee">rusted</span>
<span data-id="e">E</span><span data-id="tee">xecution</span>
<span data-id="e2">E</span><span data-id="tee">nvironment</span>

Note:
Trusted Execution Environment

vvv

## Standardization

Note:
- Over time, TEEs underwent some standardization efforts to make the concept more the same for different hardware manufacturers
- These efforts are guided by

vvv

<!-- .slide: data-background-iframe="https://globalplatform.org/" -->

Note:
- first to come up with the term TEE
- also provide an API that TEEs have to comply with

vvv

<!-- .slide: data-background-iframe="https://confidentialcomputing.io/" -->

Note:
And there is also the CCC

vvv

> A TEE consists of an isolated environment in which Trusted Applications can execute without the interference of the (untrusted) OS.

Note:
- All these efforts have at least led to a definition of a TEE

vvv

### TrustZone is not a TEE
Note:
- Enables TEE

vvv

<!-- .slide: data-background-iframe="https://www.trustedfirmware.org/projects/op-tee/" -->

Note:
- Most well-known TEE for TrustZone
- Implements GP API
- And backed by Linaro
- Readable documentation

vvv

## What's missing?

Note:
- So we can spawn TEEs which are secure from their OS.
- What can be missing?

vvv

<img height="400" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.imgflip.com%2F4qv85n.jpg&f=1&nofb=1&ipt=8aca72c4a3bc2c82cdef8b5f91b0144289ec34992429ed3c340a2ecb22deeec1&ipo=images" >

Note:
- The problem is that we now cannot see what happens inside the application anymore
- To see why that is a problem, let's go back to our patat analogy

vvv

### My restaurant

<img class="r-stretch" src="./dist/img/kwalitaria.jpg" />

Note:

And Mark comes to visit me. I want to give him my fries in exchange for his money. However, he is paranoid and doesn't trust me because he can't see me making the fries.

vvv

<img class="r-stretch" src="https://static.fanpage.it/wp-content/uploads/sites/22/2020/09/iStock-618214356.jpg" />


Note:
I'm like, Mark come on, you see these fries. They look good. But Mark insists. He wants some kind of evidence that I did actually prepare the fries like
it should be done.

vvv

## How can we convince Mark?

We need to show him some proof

Note:
- Preferably without Mark watching my every move in the kitchen
- Health inspection report

vvv

<!-- .slide: data-auto-animate data-auto-animate-unmatched="false" -->
<img height="400" src="dist/img/what-happens-here.png"/>

Note:
- If we translate that to our computer
- We want to know what happens here without sacrificing the benefits

---

<!-- .slide: data-auto-animate -->

# Attestation

vvv

<!-- .slide: data-auto-animate -->

# Attestation
Prove to another<span data-id="1" style="font-size: 0;">remote</span> party that you run trusted software

Note:
- There is also Remote attestation

vvv

<!-- .slide: data-auto-animate -->

## Remote
# Attestation
Prove to another <span data-id="1">remote</span> party that you run trusted software

vvv

### We love standards

vvv

## RATS

<img height="300" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.ytimg.com%2Fvi%2FvURhQy2Sk18%2Fmaxresdefault.jpg&f=1&nofb=1&ipt=1fca7ee512d7e896bb1582511d9dea8b8bb293065b0ab5356dc67f1628839e99&ipo=images" />

vvv

<!-- .slide: data-background-iframe="https://www.rfc-editor.org/rfc/rfc9334.html" -->

vvv

<!-- .slide: data-auto-animate -->

#### Terminology (<span data-id="restaurant">restaurant</span><span data-id="TrustZone" style="font-size: 0pt">TrustZone</span>)

<span class="fragment fade-in-then-semi-out" data-fragment-index="1" data-id="attester">Attester -></span> <span data-id="me" class="fragment fade-in-then-semi-out" data-fragment-index="1">Me</span><span data-id="ta" style="font-size: 0;">TA</span>

<span class="fragment fade-in-then-semi-out" data-fragment-index="2" data-id="claim">Claim -></span> <span data-id="restaurant" class="fragment fade-in-then-semi-out" data-fragment-index="2">Information about my restaurant</span><span data-id="info" style="font-size: 0;">Information about TA and device</span>

<span class="fragment fade-in-then-semi-out" data-fragment-index="3" data-id="evidence">Evidence -></span> <span data-id="health-report" class="fragment fade-in-then-semi-out" data-fragment-index="3">The health inspection report</span><span data-id="claims" style="font-size: 0;">Set of claims</span>

<span class="fragment fade-in-then-semi-out" data-fragment-index="4" data-id="verifier">Verifier -></span> <span data-id="health-inspector" class="fragment fade-in-then-semi-out" data-fragment-index="4">The health inspector</span><span data-id="manufacturer" style="font-size: 0;">Device Manufacturer</span>

<span class="fragment fade-in-then-semi-out" data-fragment-index="5" data-id="rp">Relying Party -></span> <span data-id="mark" class="fragment fade-in-then-semi-out" data-fragment-index="5">Mark</span> <span data-id="software-vendor" style="font-size: 0;">Software Vendor of the TA</span>

Note:
- And with these terms, we have some models for attestation

vvv

<!-- .slide: data-auto-animate -->

#### Terminology (<span data-id="restaurant" style="font-size: 0;">restaurant</span><span data-id="TrustZone">TrustZone</span>)

<span data-id="attester">Attester -></span> <span data-d="me" style="font-size: 0;">Me</span><span data-id="ta">Trusted Application</span>

<span data-id="claim">Claim -></span> <span data-id="restaurant" style="font-size: 0;" >Information about my restaurant</span><span data-id="info">Information about TA and device</span>

<span data-id="evidence">Evidence -></span> <span data-id="health-report" style="font-size: 0;" >The health inspection report</span><span data-id="claims">Set of claims</span>

<span data-id="verifier">Verifier -></span> <span data-id="health-inspector" style="font-size: 0;" >The health inspector</span><span data-id="manufacturer">Device Manufacturer</span>

<span data-id="rp">Relying Party -></span> <span data-id="mark" style="font-size: 0;" >Mark</span><span data-id="software-vendor">Software Vendor of the TA</span>

vvv

<div style="float: left; width: 50%;">
<h3>Passport<br> Model</h3>
<img src="https://learn.microsoft.com/en-us/azure/confidential-computing/media/attestation-solutions/passport-model-computing.png" />
</div>

<div style="float: left; width: 50%;">
<h3>Background Check Model</h3>
<img src="https://learn.microsoft.com/en-us/azure/confidential-computing/media/attestation-solutions/background-check-model-computing.png" />
</div>


---

## My Literature Research

vvv

## Why?

Note:
- I wanted to know if there is already something out there that is usable
- If that is not really the case, learn from the existing research and see how they did it

vvv

## How?

Note:
- To make my life easier
- Came up with some features for attestation
- To be able to compare

vvv

<!-- .slide: data-background-iframe="./dist/thesis.pdf#page=13" -->

vvv

<img src="./dist/img/winner.png" height="400" />

vvv

But can we make one ourselves?

vvv

<div style="float: left; width: 50%;">
<h3>Passport<br> Model</h3>
<img src="https://learn.microsoft.com/en-us/azure/confidential-computing/media/attestation-solutions/passport-model-computing.png" />
</div>

<div style="float: left; width: 50%;">
<h3>Background Check Model</h3>
<img src="https://learn.microsoft.com/en-us/azure/confidential-computing/media/attestation-solutions/background-check-model-computing.png" />
</div>

vvv

How to achieve this by sharing the least amount of information?

---

# Building Blocks

vvv

## Merkle Trees

vvv

<div class="r-stack" height="500">
<img src="https://c8.alamy.com/comp/D5AYH7/german-chancellor-angela-merkel-waters-a-tree-inastana-kazakhstan-D5AYH7.jpg" />
<img class="fragment fade-in-out" src="https://media.gettyimages.com/photos/august-2018-armenia-yerevan-german-chancellor-angela-merkel-plants-a-picture-id1022382344?s=594x594" />
<img class="fragment fade-in-out" src="https://seebitcoin.com/wp-content/uploads/2016/07/merkeltree.jpg" />
<img class="fragment fade-in-out" height="500" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia.gettyimages.com%2Fphotos%2Fgerman-chancellor-angela-merkel-poses-in-front-of-a-christmas-tree-at-picture-id988402718&f=1&nofb=1&ipt=17d8309f791f567d71ad7149dcd87e4cff297b6647aabeea8841eac2803d2664&ipo=images" />
<img class="fragment fade-in-out" src="https://media.gettyimages.com/photos/german-chancellor-angela-merkel-walks-past-a-christmas-tree-with-picture-id459989886?s=594x594" />
<img class="fragment fade-in-out" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.reviewjournal.com%2Fwp-content%2Fuploads%2F2019%2F09%2F12760813_web1_911treeB.jpg%3Fcrop%3D1&f=1&nofb=1&ipt=6d7d95ff59259731bfd1706145ce589934210f983d9b8c7d4ce4ed2450b10359&ipo=images" />
<img class="fragment fade-in-out" src="https://media.gettyimages.com/photos/german-chancellor-angela-merkel-stands-in-front-of-the-newly-erected-picture-id625319886" />
<img class="fragment fade-in-out" src="https://external-preview.redd.it/ji6SZuRHCvlj4HySdLFlVgjZld2Z86AY44MkiCl0ST8.jpg?auto=webp&s=1af004174834f48ddae2f85a56be2036279c9307" />
<img class="fragment fade-in-out" src="https://www.telegraph.co.uk/multimedia/archive/00685/g8-tree-planting_685783n.jpg" />
</div>

vvv

<img class="r-stretch" src="https://kjoo.be/wp-content/uploads/2022/08/1658729781226-697x1024.jpg" />

vvv

##### From the one who brought you cryptographic hash functions

$H(x) \rightarrow y$

And no function $F$ such that

$F(y) \rightarrow x$

Note:

You might know them as SHA-2/3 or BLAKE2 etc.

vvv

<img class="r-stretch" src="./dist/img/merkle-tree.png" />

vvv

<!-- .slide: data-auto-animate -->
### Merkle Proof

vvv

<!-- .slide: data-auto-animate -->
### Merkle Proof

Given the Root ➡️ prove $A$

I only need $H_B$ and $H_{CD}$

<img class="r-stretch" src="./dist/img/merkle-tree-proof.png" />

vvv

*Claims* are the leaves

Merkle Tree Root as *Evidence*.

vvv

<img class="r-stretch" src="./dist/img/evidence-in-tree.png" />

vvv

How to get the Merkle Tree across?

Note:
- We now have the way in which we want to calculate our data. How do we get this safely to the relying party and verifier?

---

<img height="300" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.mememaker.net%2Fstatic%2Fimages%2Fmemes%2F4471846.jpg&f=1&nofb=1&ipt=a34258f40ab9420c219dc32619a7b5d281b07a6d8d0817584baf1c924bc388b3&ipo=images" />

Note:
- Since rolling your own crypto is always a bad idea
- We use noise

vvv

<!-- .slide: data-background-iframe="http://noiseprotocol.org/" -->

Note:
- a framework for creating your own cryptographic protocol
- with some nice benefits and flexibility
- You use their building blocks to create your own protocol

vvv

A framework for creating your handshake protocol

Used by Wireguard, WhatsApp, Signal...

Note:
- Not something random I found on the internet.

vvv

### What is it made of?

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="dh" -->

## Diffie Hellman

<img height="300" style="transform: scaleX(-1);" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.VLlW7oTGbDqr_SjBBnSw4AHaFH%26pid%3DApi&f=1&ipt=05b2bda7227bb5a33d845fb42925caa24b294de66d35912dd65ae5bc1c79c18f&ipo=images" />

vvv

We've already seen them today!

vvv

<img class="r-stretch" src="https://kjoo.be/wp-content/uploads/2022/08/1658729781226-697x1024.jpg" />

Note:
- Isn't it nice to know that these crypto geniuses knew each other?

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="dh" -->

## Diffie Hellman

I know $a$ and $g$ <!-- .element: class="fragment fade-in"-->

You know $b$ and $g$ <!-- .element: class="fragment fade-in"-->

I send $g^a$ <!-- .element: class="fragment fade-in"-->

You send $g^b$ <!-- .element: class="fragment fade-in"-->

$(g^a)^b = (g^b)^a = K$ <!-- .element: class="fragment fade-in"-->

Note:
- We are now past this, but the idea is still the same

vvv

### Other Building Blocks

Hash Function (**SHA-256**)

Symmetric Encryption Function (**AES-256**)

vvv

Back to NOISE

We use the XK variant

Note:
Explain the XK variant

vvv

## What does that mean?

vvv

### Key Types

<div style="float: left; width: 50%;">
<h4>Ephemeral</h4>
<p>Generated on the fly</p>
</div>

<div style="float: left; width: 50%;">
<h4>Static</h4>
<p>Used more often</p>
</div>

vvv

<img class="r-stretch" src="./dist/img/init-resp.png" />

vvv

<img class="r-stretch" src="./dist/img/handshake-total.png" />

vvv

Authentication

Secrecy

Forward Secrecy

Secure Channel

vvv

### How can you be so sure?

vvv

<!-- .slide: data-background-iframe="https://tamarin-prover.github.io/" -->

Note:
- I've formally proven everything in the Tamarin prover
- A way to check if claims about your crypto hold
- Its own language

vvv

<!-- .slide: data-background-iframe="http://localhost:3001" -->

---

<!-- .slide: data-auto-animate data-auto-animate-duration="0.0" -->

<img class="r-stretch" src="./dist/img/full-1.png" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-duration="0.0" -->

<img class="r-stretch" src="./dist/img/full-2.png" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-duration="0.0" -->

<img class="r-stretch" src="./dist/img/full-3.png" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-duration="0.0" -->

<img class="r-stretch" src="./dist/img/full-4.png" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-duration="0.0" -->

<img class="r-stretch" src="./dist/img/full-5.png" />

vvv

## Implementation

Rust PoC

Library

OP-TEE in QEMU

WIP

---


<img style="float: left; width: 50%;" class="r-stretch" src="./dist/img/max-patat.png" />

## Summary

Carve potato up -> TrustZone <!-- .element: class="fragment fade-in-then-semi-out"-->

Show the health inspection report -> Attestation <!-- .element: class="fragment fade-in-then-semi-out"-->

NOISY Trees make PATAT <!-- .element: class="fragment fade-in-then-semi-out"-->
