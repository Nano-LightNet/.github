# Nano - Light Network
#### Developed by the Nano Community Foundation
#### Nano Light Network is a protocol which allows for Protocol Improvements.
#### We develop the light net implementation of Nano Node.

# Example of Network Upgrade
#### Light Cookie = 30 Random Bytes
#### Cookie = Light Net Protocol Version + Minimum Light Net Protocol Version + Light Cookie
| Sender | Network | Message Type | Body | Extensions |
|   --   |   ---   |      --      |  --  |     --     |
| Client (Light Node) | Nano/Native | NodeIDHandshake (0x0a) | { Cookie } | 0x8001
| Server (Light Node) | Nano/Native | ProtocolUpgrade (0x1f) | Empty | 0x0000
| Client (Light Node) | Nano/Native | ProtocolUpgrade (0x1f) | Empty | 0x0000
| Server (Light Node) | Light | NodeIDReq (0x01) | { NodeID, Light Cookie } | 0x0001
| Client (Light Node) | Light | NodeIDReq (0x01) | { NodeID } | 0x0000
| Server (Light Node) | Light | NodeIDAck (0x02) | { { Representative, Signature }, { Representative, Signature }, Message Signature } | 0x0002
| Client (Light Node) | Light | NodeIDAck (0x02) | { Message Signature } | 0x0000


# Example of Light Node connecting to Nano Node
#### Light Cookie = 30 Random Bytes
#### Regular Cookie = 32 Random Bytes
#### Cookie = Light Net Protocol Version + Minimum Light Net Protocol Version + Light Cookie
| Sender | Network | Message Type | Body | Extensions |
|   --   |   ---   |      --      |  --  |     --     |
| Client (Light Node) | Nano/Native | NodeIDHandshake (0x0a) | { Cookie } | 0x8001
| Server | Nano/Native | NodeIDHandshake | { Regular Cookie, { NodeID, Signature } } | 0x0003
| Client (Light Node) | Nano/Native | NodeIDHandshake | { { NodeID, Signature } } | 0x0002
