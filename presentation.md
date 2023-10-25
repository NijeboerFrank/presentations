<!-- .slide: data-auto-animate data-auto-animate-id="patat" -->

## Master Thesis

Frank Nijeboer

<span data-id="protocol">A</span>
<span data-id="p">P</span><span data-id="protocol">rotocol for</span>
<span data-id="at">AT</span><span data-id="protocol">testation in</span>
<span data-id="a">A</span><span data-id="protocol">rm</span>
<span data-id="t">T</span><span data-id="protocol">rustZone</span>

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

---


## Cutting Potatoes
<img class="r-stretch" src="https://fromscratchfast.com/wp-content/uploads/2020/06/Baked-French-Fries-Recipe-2.jpg" />

## ⬇️

## Compartmentalization

vvv

##

<!-- .slide: data-background-iframe="" -->

## Security is a hot topic

Note:
And I don't say that just because I chose the security master

---

<!-- .slide: data-auto-animate -->

## Compartmentalization

Note:
Just splitting up is not enough. We need something more

vvv


<!-- .slide: data-auto-animate -->

## Compartmentalization

#### <span data-id="towards">Can we improve </span><span data-id="hardware-based" style="font-size: 0;">Hardware-based </span><span data-id="security">security</span><span data-id="question-mark">?</span>

vvv

<!-- .slide: data-auto-animate -->

#### <span data-id="towards" style="font-size: 0;">Can we improve </span><span data-id="hardware-based">Hardware-based </span><span data-id="security">security</span><span data-id="question-mark" style="font-size: 0;">?</span>

Note:
We can try with hardware based security

vvv

<!-- .slide: data-transition="zoom-out" -->

<h3 class="fragment fade-in-then-semi-out" data-fragment-index="1">Intel SGX</h3>
<h3 class="fragment fade-in-then-semi-out" data-fragment-index="2">RISC-V MultiZone</h3>

<div class="r-stack">
<img src="./dist/img/sgx.jpg" class="fragment fade-in-then-out" height="200" data-fragment-index="1" />
<img src="./dist/img/multizone.jpg" class="fragment fade-in-then-out" height="200" data-fragment-index="2" />
<img src="./dist/img/Arm-TrustZone-Logo-2337384223.png" class="fragment fade-in-then-out" height="200" data-fragment-index="3" />
</div>

Note:
Most hardware designers nowadays have some form of it. These are some examples. In our case, we are, obviously interested in TrustZone.

vvv

<!-- .slide: data-auto-animate data-transition="zoom-in" -->

## TrustZone

Old Technology <!-- .element: class="fragment fade-in"-->

Normal World <!-- .element: class="fragment fade-in"-->

Secure World <!-- .element: class="fragment fade-in"-->

vvv

<!-- .slide: data-auto-animate -->

<div class="container">
<div class="col">
<img src="dist/img/trustzone_layout.png"/>
</div>

<div class="col">
<h2>TrustZone</h2>
</div>
</div>

---

<!-- .slide: data-auto-animate data-auto-animate-id="tee" -->

<span data-id="t" data-auto-animate-delay="0" style="display-inline-block; color: #224099; font-size: 120px;">T</span><span data-id="tee" data-auto-animate-delay="0.1" style="display-inline-block; font-size: 0px">rusted</span>
<span data-id="e" data-auto-animate-delay="0.1" style="display-inline-block; color: #224099; font-size: 120px;">E</span><span data-id="tee" data-auto-animate-delay="0.2" style="display-inline-block; font-size: 0px">xecution</span>
<span data-id="e2" data-auto-animate-delay="0.2" style="display-inline-block; color: #224099; font-size: 120px;">E</span><span data-id="tee" data-auto-animate-delay="0.3" style="display-inline-block; font-size: 0px">nvironments</span>

Note:

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="tee" data-auto-animate-easing="cubic-bezier(0.770, 0.000, 0.175, 1.000)" data-auto-animate-duration="1.2" -->

<span data-id="t">T</span><span data-id="tee">rusted</span>
<span data-id="e">E</span><span data-id="tee">xecution</span>
<span data-id="e2">E</span><span data-id="tee">nvironments</span>

Note:
Trusted Execution Environments

vvv

## Standardization

GlobalPlatform

Confidential Computing Consortium

Note:
GlobalPlatform is an organization which created some standards wrt TEEs.
That means APIs etc.

vvv

> A TEE consists of an isolated environment in which Trusted Applications can execute without the interference of the (untrusted) OS.

vvv

## So what's up?

vvv

<img height="400" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.imgflip.com%2F4qv85n.jpg&f=1&nofb=1&ipt=8aca72c4a3bc2c82cdef8b5f91b0144289ec34992429ed3c340a2ecb22deeec1&ipo=images" >

vvv

<img class="r-stretch" src="dist/img/trustzone_layout.png"/>

---

# Attestation

vvv

<img class="r-stretch" src="./dist/img/max-patat.png" />

vvv

### My restaurant

<img class="r-stretch" src="./dist/img/kwalitaria.jpg" />

Note:

And Mark comes to visit me. I want to give him my fries in exchange for his money. However, he doesn't trust me because he can't see me making the fries.

vvv

<img class="r-stretch" src="https://static.fanpage.it/wp-content/uploads/sites/22/2020/09/iStock-618214356.jpg" />


Note:
I'm like, Mark come on, you see these fries. They look good. But Mark insists. He wants some kind of evidence that I did actually prepare the fries like
it should be done.

vvv

<img class="r-stretch" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ficons-for-free.com%2Ficonfiles%2Fpng%2F512%2Finspection-131964752898110361.png&f=1&nofb=1&ipt=df7c9e017bab4e6d03128780319465a4023e859ab060077b5fca0c5213c991f9&ipo=images" />

Note:
He wants some kind of inspection report. And that is what attestation entails. With Attestation one party can prove to another that it is running trusted software that has not been subject to any tampering.

vvv

# Attestation Terminology <!-- .element: class="r-fit-text" -->

vvv

## RATS

<img height="300" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.ytimg.com%2Fvi%2FvURhQy2Sk18%2Fmaxresdefault.jpg&f=1&nofb=1&ipt=1fca7ee512d7e896bb1582511d9dea8b8bb293065b0ab5356dc67f1628839e99&ipo=images" />

vvv

<!-- .slide: data-background-iframe="https://www.rfc-editor.org/rfc/rfc9334.html" -->

vvv

Attester -> Me

Claim -> Information about the process

Evidence -> The health inspection report

Verifier -> The health inspector

Relying Party -> Mark

vvv

Insert image about the setups that are possible

How to achieve this by sharing the least amount of information?

---

## Merkle Trees

vvv

Insert merkle tree image

vvv

How should that work for our protocol?

Claims as leaves. Merkle Tree as evidence.

vvv

How to get the Merkle Tree accross?

---

<img height="300" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.mememaker.net%2Fstatic%2Fimages%2Fmemes%2F4471846.jpg&f=1&nofb=1&ipt=a34258f40ab9420c219dc32619a7b5d281b07a6d8d0817584baf1c924bc388b3&ipo=images" />

vvv

<!-- .slide: data-background-iframe="http://noiseprotocol.org/" -->

vvv

A framework for creating your handshake protocol

Used by wireguard, whatsapp, signal...

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="dh" -->

## Diffie Hellman

<img height="300" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.VLlW7oTGbDqr_SjBBnSw4AHaFH%26pid%3DApi&f=1&ipt=05b2bda7227bb5a33d845fb42925caa24b294de66d35912dd65ae5bc1c79c18f&ipo=images" />

vvv

<!-- .slide: data-auto-animate data-auto-animate-id="dh" -->

## Diffie Hellman

I know $a$ and $g$ <!-- .element: class="fragment fade-in"-->

You know $b$ and $g$ <!-- .element: class="fragment fade-in"-->

I send $g^a$ <!-- .element: class="fragment fade-in"-->

You send $g^b$ <!-- .element: class="fragment fade-in"-->

$(g^a)^b = (g^b)^a = K$ <!-- .element: class="fragment fade-in"-->

vvv

Back to noise

We use the XK variant

Note:
Explain the XK variant

vvv

Insert total image for the handshake here.

---

### So the final version for PATAT is

vvv

Insert total PATAT image here

vvv

## Implementation

Rust

Library

Application

OP-TEE in QEMU

---

## Summary

Carve potato up -> TrustZone <!-- .element: class="fragment fade-in-then-semi-out"-->

Show the health inspection report -> Attestation <!-- .element: class="fragment fade-in-then-semi-out"-->

NOISY Trees make PATAT <!-- .element: class="fragment fade-in-then-semi-out"-->
