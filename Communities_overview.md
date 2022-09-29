# On BGP Community flavours

Currently in BGP, there are three variants of so-called 'Communities', and a
fourth one is around the corner. This document tries to summarize and compare
the essentials of all these.

First, a quick introduction of all four types: original *Communities*, *Extended
Communities*, *Large Communities*, and the upcoming *Community Container* type
carrying *Wide Communities*.

## Communities

The original Communities, Path Attribute typecode 8, described in 
[RFC1997](https://datatracker.ietf.org/doc/html/rfc1997) from 1996.

Fixed size of four octets: the first two octets encode a 16-bit ASN, the last
two octets represent the community.

Well-known communities are of this type.


## Extended Communities


Introducing a larger range and some form of structure, Path Attribute type code
16, described in
[RFC4360](https://datatracker.ietf.org/doc/html/rfc4360) from 2006.

Fixed size of eight octets, containing a Type (one or two octets) and a Value
(seven or six octets, depending on the size of the Type).
Types of one octet are called Regular types, the two octet types are called
Extended types. The first octet determines whether the community is of class Regular
or Extended, but this is not encoded in the structure itself: the class is
specified in an IANA registry.

The structure of the value depends on the type. The RFC defines several,
including:

  * the 'Two-Octet AS Specific' type, where the six first two octets of the
value represent an AS, and the last four octets can represent anything;
  * the 'IPv4 Address Specific' type, where the first four octets represent an
    IPv4 address, and the last two octets represent any value.

These two examples already show how Extended Communities are less
straight-forward to interpret and represent compared to conventional and Large
Communities.

### Wire format
```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |  Type high    |  Type low(*)  |                               |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+          Value                |
  |                                                               |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```


## Large Communities

Introducing again a larger attribute, Large Communities are twelve octets in
size and do not carry a type. With twelve octets at disposal for actual values,
Large Communities are the first variant where two 32-bit ASNs can be
represented, something the first two Community variants are not capable of.

Described in [RFC 8092](https://www.rfc-editor.org/rfc/rfc8092.html) from 2017.


### Wire format

```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                      Global Administrator                     |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                       Local Data Part 1                       |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                       Local Data Part 2                       |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```


## Community Containers (Wide Communities)

After the two attempts to increase the fixed size with a couple more bytes, the
[currently ongoing
effort](https://datatracker.ietf.org/doc/draft-ietf-idr-wide-bgp-communities/)
for the Community Container path attribute enables for variably sized
communities.

Community Containers add a layer of hierarchy, as they are indeed containers.
So, the Path Attribute carries one or multiple Containers, and the Containers
themselves carry a series of types, each prefaced with the Common Header.

Container Type 1 is the BGP Wide Community. It consists of a fixed twelve octets
plus a variable number of TLVs. The first twelve octets are the Community Value
(so the community number), the source AS, and the context AS, all four-octet
values.

The draft defines three of such TLVs, or to be exact (also see the wire format
below), three *Sub-Types*. These are the *Target(s) TLV*, the *Exclude Target(s)
TLV* and *Parameters TLV*.

The first two are used to specify 'where' actions related to a community value
should be applied (or not). These are represented using *Atom TLVs*, of which
the draft defines eight types, including a 'Autonomous System Number List',
'Prefix Lists' for both IPv4 and IPv6, and more.

The third Sub-Type, the Parameters TLV, contains input for executing the actions
for that community. These are also comprised of Atom TLVs, and their semantics
are defined by the wide community.


### Wire format

#### Common Header
```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |             Type              |    Flags  |C|T|   Reserved    |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |            Length             |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```


#### Wide Community
```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |I|                      Community Value                        |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                        Source AS Number                       |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                       Context AS Number                       |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                                                               |
  |                        TLVs (optional)                        |
  |                                                               |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

#### TLVs
```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+
  |   Sub-Type    |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |            Length             |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                         Value (variable)                      |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

#### Atoms
```txt
   0                   1                   2                   3
   0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
  +-+-+-+-+-+-+-+-+
  |     Type      |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |            Length             |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
  |                         Value (variable)                      |
  +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

# Overview

| RFC                                                                                | type                 | path attribute                            | size       | structure        | flags                      | canonical repr     | reserved values                              |
| ---                                                                                | ------               | --:                                       | --:        | --:              | --                         | --                 | --                                           |
| [RFC1997](https://datatracker.ietf.org/doc/html/rfc1997)                           | original             | 8                                         | 4          | value            | none                       | 1234:666           | 0:xxx , 65535:xxx                            |
| [RFC4360](https://datatracker.ietf.org/doc/html/rfc4360)                           | extended communities | 16                                        | 8          | type+value       | auth+transitivity          | ROUTE-TARGET-AS4:65536:1 |                                              |
| [RFC8092](https://www.rfc-editor.org/rfc/rfc8092.html)                             | large communities    | 32                                        | 12         | value            | none                       | 64496:4294967295:2 | 0:xxx:yyy, 65535:xxx:yyy, 4294967295:xxx:yyy |
| [draft](https://datatracker.ietf.org/doc/html/draft-ietf-idr-wide-bgp-communities) | wide communities*    | 34 (Community Container, temp assignment) | 12..~65k** | value+optionals* | transitivity+confederation | too complex?       |                                              |


*: As aforementioned, Wide Communities are represented with an additional layer
compared to the other community variants, i.e. the Container. The complete
structure would thus include the Common header, but that does not carry any
'value parts'.

**: The draft does not specify any upper limit in terms of size, but the length
field in the Common header of the Container is 16 bits.



# In practice

## Well-known communities

The term 'well-known community' applies to the original RFC1997 communities,
i.e. the four octet sized ones. None of the later variants seem to have
similarly defined values. The Wide Communities draft recommends to use original
communities to distribute such well-known communities when these are
'non-Autonomous System specific'. Whether or not the well-known values have any
special meaning when used in a Wide Community is not described in the draft.

In other words, when dealing with 'well-known communities', those are Path
Attribute typecode 8 conventional Communities.

Common well-known communities include:

| raw value  | signal              |
| --         | --                  |
| 0xFFFF0000 | GRACEFUL_SHUTDOWN   |
| 0xFFFFFF01 | NO_EXPORT           |
| 0xFFFFFF02 | NO_ADVERTISE        |
| 0xFFFFFF03 | NO_EXPORT_SUBCONFED |
| 0xFFFFFF04 | NOPEER              |
| 0xFFFF029A | BLACKHOLE           |

Refer to the [IANA registry](https://www.iana.org/assignments/bgp-well-known-communities/bgp-well-known-communities.xhtml) for a complete overview.


## Conventional vs Large Communities

Note that Large Communities are crucial for operators of four-octet ASNs. There
is simply not enough space in a conventional community (which is four octets
large) to include both a four-octet ASN and a value. Likewise, operators of
two-octet ASNs might have no need for any additional octets in the value of
communities: if the two octets in a conventional community is enough for their
signalling needs, there is no reason to use Large Communities.

## Extended Communities?

**TODO** where are these most commonly used in the wild? 

## Containers / Wide Communities?

**TODO** not observed in the wild yet, probably


# References

## IANA
  * [Well-known
Communities](https://www.iana.org/assignments/bgp-well-known-communities/bgp-well-known-communities.xhtml)
  * [Extended
Communities](https://www.iana.org/assignments/bgp-extended-communities/bgp-extended-communities.xhtml)
