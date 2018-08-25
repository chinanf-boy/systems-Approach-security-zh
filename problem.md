# {{ page.title }}

> It is true greatness to have in one the frailty of a man and the
> security of a god. *—Seneca*

## Problem: Security Attacks

Computer networks are typically a shared resource used by many
applications representing different interests. The Internet is
particularly widely shared, being used by competing businesses, mutually
antagonistic governments, and opportunistic criminals. Unless security
measures are taken, a network conversation or a distributed application
may be compromised by an adversary.

Consider some threats to secure use of, for example, the World Wide Web.
Suppose you are a customer using a credit card to order an item from a
website. An obvious threat is that an adversary would eavesdrop on your
network communication, reading your messages to obtain your credit card
information. How might that eavesdropping be accomplished? It is trivial
on a broadcast network such as an Ethernet, where any node can be
configured to receive all the message traffic on that network. Wireless
communication can be monitored without any physical connection. More
elaborate approaches include wiretapping and planting spy software on
any of the chain of nodes involved. Only in the most extreme cases
(e.g.,national security) are serious measures taken to prevent such
monitoring, and the Internet is not one of those cases. It is possible
and practical, however, to encrypt messages so as to prevent an
adversary from understanding the message contents. A protocol that does
so is said to provide *confidentiality*. Taking the concept a step
farther, concealing the quantity or destination of communication is
called *traffic confidentiality*—because merely knowing how much
communication is going where can be useful to an adversary in some
situations.

Even with confidentiality there still remains threats for the website
customer. An adversary who can't read the contents of your encrypted
message might still be able to change a few bits in it, resulting in a
valid order for, say, a completely different item or perhaps 1000 units
of the item. There are techniques to detect, if not prevent, such
tampering. A protocol that detects such message tampering provides *data
integrity*. The adversary could alternatively transmit an extra copy of
your message in a *replay attack*. To the website, it would appear as
though you had simply ordered another of the same item you ordered the
first time. A protocol that detects replays provides *originality*.
Originality would not, however, preclude the adversary intercepting your
order, waiting a while, then transmitting it—in effect, delaying your
order. The adversary could thereby arrange for the item to arrive on
your doorstep while you are away on vacation, when it can be easily
snatched. A protocol that detects such delaying tactics is said to
provide *timeliness*. Data integrity, originality, and timeliness are
considered aspects of the more general property of *integrity*.

Another threat to the customer is unknowingly being directed to a false
website. This can result from a Domain Name System (DNS) attack, in
which false information is entered in a DNS server or the name service
cache of the customer's computer. This leads to translating a correct
URL into an incorrect IP address—the address of a false website. A
protocol that ensures that you really are talking to whom you think
you're talking is said to provide *authentication*. Authentication
entails integrity, since it is meaningless to say that a message came
from a certain participant if it is no longer the same message.

The owner of the website can be attacked as well. Some websites have
been defaced; the files that make up the website content have been
remotely accessed and modified without authorization. That is an issue
of *access control*: enforcing the rules regarding who is allowed to do
what. Websites have also been subject to denial of service (DoS)
attacks, during which would-be customers are unable to access the
website because it is being overwhelmed by bogus requests. Ensuring a
degree of access is called *availability*.

In addition to these issues, the Internet has notably been used as a
means for deploying malicious code that exploits vulnerabilities in end
systems. *Worms*, pieces of self-replicating code that spread over
networks, have been known for several decades and continue to cause
problems, as do their relatives, *viruses*, which are spread by the
transmission of infected files. Infected machines can then be arranged
into *botnets*, which can be used to inflict further harm, such as
launching DoS attacks.

Although the Internet was designed with the redundancy to survive
problems such as the disruption of a link or router, it was not
originally designed to provide the kind of security we have been
discussing. Internet security mechanisms have essentially been patches.
If a comprehensive redesign of the Internet were to take place,
integrating security would likely be the foremost driving factor. That
possibility makes this chapter all the more pertinent.

There are many tools today for securing networked systems, ranging from
various forms of cryptography to specialized devices such as firewalls.
This chapter will provide an introduction to these tools with a
particular focus on the use of cryptographic methods to improve network
security. Improving the security of networks continues to be a field of
rapid change and considerable research effort.
