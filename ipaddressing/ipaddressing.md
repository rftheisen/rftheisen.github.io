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

![clientserver](clientserver.png)

Each message generated for transmission over a network has a source and destination IP
address (like we saw in the addressing structure highlighted in Diagram 1-2). We must also
note that the IP address has a specific format. This formatting is called **Dotted Decimal**.
Take the IP address **192.168.0.5** for example, this is an IPv4 address and you’ll notice that
it is made up of **4 decimal numbers** separated by **4 octets** (spaces between periods).
The IPv4 address has 2 portions: Network & Host. The **Network** & **Host** portion of the
IPv4 address are critical to understanding how you should apply an addressing scheme to a
network. Let’s compare a network to a neighborhood. A neighborhood is a grouping of
houses in as part of a town or district and a network is a grouping of computers. Each
house in a neighborhood has a specific address that is unique to that house. Each computer
in a network has an IP address that is unique to that computer. Please understand that the
Network portion of an IP address represents the whole network (neighborhood) therefore
every computer that is going to be on the same network should have an IP address that has
the same network portion. “Alright great the network portion is important because it
summarizes an entire network but what about the host portion you mentioned? Is this like a
game show host?” No, it is not at all like a game show host! The host portion of an IP
address should be unique to every computer. “How can I tell which portion of the IP
address is reserved for the network and which is assignable to hosts?” You know what….. I
am so glad you asked! Enter the Subnet Mask.

## The Subnet Mask

An IPv4 address would be useless without the Subnet Mask. The Subnet Mask is an
address that defines the network and host portion of an IP address. Check this out:

192.168.0.10
255.255.255.0

Let’s use another metaphor to make sense of this. If an IP address is a phone number for
a computer then the Subnet Mask is the area code. In this case, where there is a 255 in
the Subnet Mask the number in the corresponding octet in the IP address must match.
Where there is a 0 in the Subnet Mask the number in the corresponding octet in the IP
address can change and must be different on all devices connected to the network.
Using this same example what is the network portion of this IP address?
________________________

If you said 192.168.0 is the network portion then you are absolutely……….. Correct!

What is the host portion? ___________________________

If you said the last octet then you would be correct!

Alright so now we must understand how and why 255 represents the network bits. Here
is where that math we talked about earlier comes in. Trust me it’s not rocket science or
calculus, its all just 1s and 0s.