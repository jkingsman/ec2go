# ec2go

`ec2go` is a bash script to parse the type of AWS resource (e.g. `i-0201ec6207852de37` is an EC2 instance) and automatically open the corresponding AWS Console webpage to search for that resource.

This can simplify troubleshooting and save clicks to get from resource ID to console page.

## Installation

This script can be installed anywhere on your path or wherever else you'd like to put it for maximum convenience. This script requires the `aws` CLI tools to be installed.

```
sudo wget -O /usr/local/bin/ec2go https://raw.githubusercontent.com/jkingsman/ec2go/master/ec2go
sudo chmod +x /usr/local/bin/ec2go

ec2go <resource ID>
```

## Usage:

`ec2go.sh [profile] <resource ID>`

This will give a best-effort to open the appropriate console for the given resource in the browser.

If provided, `profile` indicates the AWS user configuration profile to use for region selection. Defaults to `default`.

`<resource ID>` must be one of the following formats:

| Resource ID Example | Resource Type |
|-|-|
| `i-0201ec6207852de37` | instance |
| `vol-0201ec6207852de37` | volume |
| `snap-0201ec6207852de37` | snapshot |
| `eni-attach-0201ec6207852de37` | network-interface-attachment |
| `eni-0201ec6207852de37` | network-interface |
| `eipalloc-0201ec6207852de37` | elastic-ip-allocation |
| `eipassoc-0201ec6207852de37` | elastic-ip-association |
| `vpc-0201ec6207852de37` | vpc |
| `subnet-0201ec6207852de37` | subnet |
| `rtb-0201ec6207852de37` | route-table |
| `acl-0201ec6207852de37` | network-acl |
| `dopt-0201ec6207852de37` | dhcp-options |
| `igw-0201ec6207852de37` | internet-gateway |
| `pcx-0201ec6207852de37` | vpc-peering-connection |
| `sg-0201ec6207852de37` | security-group |
| `vpce-0201ec6207852de37` | vpc-endpoint |
| `ami-0201ec6207852de37` | image |
| `cgw-0201ec6207852de37` | customer-gateway |
| `vpn-0201ec6207852de37` | vpn-connection |
| `vgw-0201ec6207852de37` | vpn-gateway |
| `cvpn-endpoint-0201ec6207852de37` | client-vpn-endpoint |
| `00a726e2-5125-40ae-a5c0-b9e13f71f629` | reservation |

## Contributing

Please feel free to expand this utility with new resources if I've missed any that have a trivial search interface.

The script simply applies a regex to the provided resource ID; it should be easy to spot in the script and pick the pattern up.

I'm also not super confident my cross-platform browser script is really all that great; improvement of `open_url` would be appreciated.
