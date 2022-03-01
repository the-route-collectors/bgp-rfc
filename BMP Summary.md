# BMP RFC Summaries

[RFC 7854](https://www.rfc-editor.org/info/rfc7854) BGP Monitoring Protocol (BMP)

This RFC is an introduction to the BGP Monitoring Protocol (BMP). BMP is a monitoring protocol for a BGP speaker (router) and consists of a thin layer around BGP messages with a few special messages to indicate the status of BGP connections that are set up by the monitored router and some control messages for the BMP connection to the monitored router itself.

It discusses and details the protocol format and discusses the acquisition of BMP messages from the `Adj-RIB-In` from routers, both `pre-policy` and `post-policy` (there's a flag to indicate which is sent). 

[RFC 8671](https://www.rfc-editor.org/info/rfc8671) Support for Adj-RIB-Out in the BGP Monitoring Protocol (BMP)

Updates 7854 by adding access to the `Adj-RIB-Out` RIBs. It also adds a new flag to the peer header to distinguish between `Adj-RIB-In` and `Adj-RIB-Out`.

[RFC 9069](https://www.rfc-editor.org/info/rfc9069) Support for Local RIB in the BGP Monitoring Protocol (BMP)

Updated 7854 by adding access to the Local Routing Information Base (`Loc-RIB`). The `Loc-RIB` contains the routes that have been selected by the local BGP speaker's Decision Process.