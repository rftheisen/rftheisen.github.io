# IP Addressing & Subnetting

**Why are we doing this? (The Willieverneedthis? Paradigm)**

When it comes to any process involving math many people tend to subscribe to this
mindset: “This seems really pointless! Will I ever really use this stuff!?” This mindset makes
sense but if you commit to it you can really cripple your ability to learn important concepts.
The purpose of IP addressing & Subnetting is not to make your life harder. We aren’t
learning this just to fill time. This is a skillset that is fundamental to the success of the
Networking Professional. You will even find that the math involved is easy. The hardest part
about this whole process is discovering and understanding a method that works for you. In
this packet we are going to cover IP addressing concepts and a fantastic Subnetting method
that has done wonders for me.

![youthinkinglikehomerfromTheSimpsons](homer.png)


# What is an IP address?

An Internet Protocol address is a logical identifier for a host (device with a network card) on
a network. You should know that an IP address is assigned in software. There are two
versions of IP: IPv4 and IPv6. We will be focusing on mastering IPv4 first so don’t expect to
see much about IPv6 in this packet. As of the date of this writing IPv4 is the dominant
protocol in the Enterprise Local Area Network.

# Internet Protocol version 4 (IPv4)
IPv4 has been around since the early days of the Internet. A matter of fact this first
experimental network was known as the ARPANET (Advanced Research Projects Agency
Network) and it was developed by the United States Department of Defense to address data
packets for transmission over a physical medium. Yes, you could say the Internet started as
a government experiment. This picture below is one of the first Computer Network
topologies drawn to represent the Internet (ARPANET).

![arpanet](arpanet.png)

# IPv4 Structure

![structure](structure.png)

What…… in…… the….. World is all that in that image?!?! This is probably what you are
thinking right? Don’t worry you will understand it in due time, for now just follow me.
Like many other protocols IPv4 specifies a structure for a message being sent over a
network. Let’s say you are composing an email using Microsoft Outlook. You enter the email
address of your friend in the To: field, finish your email and hit send. Immediately your’
Operating System and the drivers for your NIC (Network Interface Card) work together to
package your message inside an IPv4 packet. The process of packaging the data inside of
the packet is known as encapsulation This process is like writing a letter (email) and placing
it in an envelope (packet) to be carried to the destination by the postal service. All
information that is generated and sent over a network goes through the process of
encapsulation (remember the OSI Model!?).
