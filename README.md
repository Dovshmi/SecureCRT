# SecureCRT NetworkOps Keyword Highlighting

A collection of SecureCRT keyword-highlighting profiles for network engineers, NOC work, troubleshooting, and lab environments.

The profiles are designed mainly for **dark terminal backgrounds** and use SecureCRT regular-expression keyword highlighting to make important CLI output easier to scan.

## What gets highlighted

The profiles recognize common network output such as:

- IPv4 addresses, prefixes, subnet masks, and IPv6
- MAC addresses
- Interfaces and ports
- VLAN, C-VLAN, S-VLAN, QinQ, trunk, and access terminology
- VRF, IPVPN, MPLS, VPLS, VPRN, and routing-instance terms
- BGP, iBGP, eBGP, OSPF, RIP, EIGRP, IS-IS, LDP, and RSVP
- next-hop, gateway, route-target, route-distinguisher, AS-PATH, and route-table fields
- ARP, STP, RSTP, MSTP, LACP, LLDP, CDP, and other Layer-2 terms
- NAT, SNAT, DNAT, ACLs, route-maps, prefix-lists, and security-policy terms
- SSH, SNMP, NTP, DHCP, DNS, AAA, RADIUS, TACACS+, LDAP, PPP, PPPoE, and L2TP
- Optical diagnostics such as SFP, DDM, Tx/Rx, dBm, CRC, and FEC
- Operational states such as `UP`, `DOWN`, `ESTABLISHED`, `FULL`, `FAILED`, `LOS`, and `err-disabled`
- Dangerous commands such as `reload`, `erase`, `delete`, and `shutdown`

## Supported network platforms

The expanded profiles include patterns for several router and switch families, including:

- Cisco IOS / IOS-XE-style routers and switches
- Juniper MX and SRX
- Nokia / Alcatel 7750, 6450/6454, 6850, and 6860
- MRV optical switches
- ADTRAN / TG-style access equipment
- Generic PE / CE / Route Reflector / MSAG / MT / LNS terminology

Examples of recognized interfaces include:

```text
Gi0/1
GigabitEthernet0/1
Te0/0/0
Vlan100
Dialer0
ge-0/0/1.103
xe-0/0/1.4003
ae1.100
1/12
```

## Smart Dark Pack

The `Ron_SecureCRT_Smart_Dark_Pack` directory contains the newer profiles.

### General themes

| Theme | Description |
| --- | --- |
| `Ron_Smart_NeonMax_DkBg.ini` | Very vivid colors and fast visual scanning |
| `Ron_Smart_ArcticBlue_DkBg.ini` | Cool blue/cyan palette for long sessions |
| `Ron_Smart_PurpleCircuit_DkBg.ini` | Purple/cyan palette with strong protocol separation |
| `Ron_Smart_AmberTerminal_DkBg.ini` | Warm amber/green classic-terminal style |
| `Ron_Smart_MatrixGreen_DkBg.ini` | Green-heavy terminal theme |
| `Ron_Smart_ColorblindBlueOrange_DkBg.ini` | Blue/orange/magenta-oriented palette |
| `Ron_Smart_LowStrainSlate_DkBg.ini` | Muted colors intended to reduce visual fatigue |
| `Ron_Smart_HighContrast_DkBg.ini` | Maximum contrast for quick troubleshooting |

### Purpose-built profiles

These profiles do more than change colors. They emphasize different categories of information depending on the task.

| Profile | Best for |
| --- | --- |
| `Ron_Smart_Troubleshooting_DkBg.ini` | Errors, alarms, interface state, IPs, CRC/FEC, optical problems |
| `Ron_Smart_Routing_IPVPN_DkBg.ini` | VRF, BGP/OSPF/MPLS, next-hop, neighbors, route tables, IPVPN work |
| `Ron_Smart_Layer2_DkBg.ini` | VLAN, C-VLAN, S-VLAN, QinQ, MAC, STP/LACP/LLDP, interfaces |
| `Ron_Smart_Optical_DkBg.ini` | SFP, DDM, Tx/Rx, dBm, CRC/FEC, physical ports and optical links |
| `Ron_Smart_Minimal_DkBg.ini` | Low visual noise with only high-value operational tokens highlighted |

## Older / base profiles

The repository also contains the original Cisco keyword files and earlier NetworkOps themes:

```text
Cisco Words - DkBg.ini.ini
Cisco Words.ini.ini
Ron_NetworkOps_DkBg_v2.ini
Ron_NetworkOps_Neon_DkBg.ini
Ron_NetworkOps_Ocean_DkBg.ini
Ron_NetworkOps_CyberPurple_DkBg.ini
Ron_NetworkOps_AmberGreen_DkBg.ini
```

The Smart Dark Pack is recommended for new installations.

## Installation

### 1. Find the SecureCRT configuration directory

In SecureCRT, open:

```text
Options -> Global Options -> Configuration Paths
```

Locate your SecureCRT configuration directory.

### 2. Open the Keywords directory

Inside the configuration directory, locate or create:

```text
Keywords
```

### 3. Copy the profiles

Copy the `.ini` profiles you want to use into the `Keywords` directory.

For example:

```text
Config\Keywords\Ron_Smart_ArcticBlue_DkBg.ini
Config\Keywords\Ron_Smart_Troubleshooting_DkBg.ini
Config\Keywords\Ron_Smart_Routing_IPVPN_DkBg.ini
```

### 4. Restart SecureCRT

Completely close SecureCRT and open it again so the keyword lists are reloaded.

### 5. Select a profile

Open:

```text
Session Options
  -> Terminal
  -> Appearance
  -> Keyword Highlighting
```

Use the **List name** dropdown and select the imported profile.

> **Important:** Do not click **New...** after importing an `.ini` file. The file already defines the keyword list. Clicking `New...` with the same name can produce an **"already in use"** error.

## Recommended starting profiles

For general network work:

```text
Ron_Smart_ArcticBlue_DkBg
```

For active troubleshooting:

```text
Ron_Smart_Troubleshooting_DkBg
```

For routing / IPVPN / PE work:

```text
Ron_Smart_Routing_IPVPN_DkBg
```

For VLAN / MAC / QinQ troubleshooting:

```text
Ron_Smart_Layer2_DkBg
```

For optical access and SFP diagnostics:

```text
Ron_Smart_Optical_DkBg
```

## Example

A routing-table or interface output such as:

```text
B       10.10.10.0/24 via 192.168.1.1
O       172.16.20.0/24 via 10.1.1.2
GigabitEthernet0/1     192.168.10.1    up      up
GigabitEthernet0/2     unassigned      down    down
Neighbor 10.0.0.2      ESTABLISHED
VRF CUSTOMER_A
VLAN 103
Rx -13.7 dBm
CRC 0
```

becomes much easier to scan because addresses, interfaces, protocols, state words, VLANs, and diagnostic values are visually separated.

## Dark-background recommendation

These profiles are designed for a dark background. A good starting point is:

```text
Background: Near black
Foreground: Light gray
Font: Cascadia Mono / Consolas / another clear monospace font
Font size: 11-13
ANSI colors: Enabled
```

Using light gray instead of pure white for normal foreground text generally makes the highlighted colors easier to distinguish during long sessions.

## SecureCRT keyword highlighting reference

VanDyke provides an official example for importing keyword-highlighting `.ini` files:

https://www.vandyke.com/support/scripting/scripting-examples/import-keyword-highlighting-ini-files.html

## Notes

- The profiles change **keyword highlighting**, not the SecureCRT background or font automatically.
- Regex rule order matters. More specific operational matches are placed before generic matches where possible.
- The Smart profiles are intended for mixed-vendor environments rather than only Cisco CLI output.
- Different devices format output differently, so additional vendor-specific patterns can be added over time.

## Repository

https://github.com/Dovshmi/SecureCRT
