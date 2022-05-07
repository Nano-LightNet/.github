# Nano - Light Network
#### Developed by the Nano Community Foundation
#### Nano Light Network is a protocol which allows for Protocol Improvements.
#### We develop the light net implementation of Nano Node.

# Example of Network Upgrade
| Sender | Network | Message Type | Body | Extensions |
|   --   |   ---   |      --      |  --  |     --     |
| Client (Light Node) | Nano/Native | NodeIDHandshake (0x0a) | { Cookie } | (0x8000 \| 0b1)
| Server (Light Node) | Nano/Native | ProtocolUpgrade (0x1f) | Empty | 0
| Client (Light Node) | Nano/Native | ProtocolUpgrade (0x1f) | Empty | 0
