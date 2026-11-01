# Incident Report Analysis: ICMP Flood Attack

## Summary

Our organization recently experienced a denial of service (DoS) attack that disrupted the internal network for two hours. An attacker flooded the network with ICMP packets, which caused our network services to suddenly stop responding and kept normal internal traffic from reaching any network resources. The incident management team responded by blocking incoming ICMP packets, taking all non-critical network services offline, and then restoring critical network services first, followed by all non-critical network systems and services.

## Identify

Our cybersecurity team investigated the security event and found that the attacker had sent a flood of ICMP pings into the company's network through a firewall that had not been properly configured. This misconfiguration allowed the attacker to overwhelm the company's network with a DoS ICMP flood attack, disrupting the internal network and its services for two hours.

## Protect

To address this security event and prevent similar incidents from compromising the company's network in the future, the network security team added a new firewall rule that limits how many ICMP packets can come in over a given period of time. The team has also set up an IDS/IPS to filter out ICMP traffic with suspicious characteristics.

## Detect

To better detect attacks like the DoS ICMP flood attack in the future, the network security team has installed network monitoring software that flags unusual traffic patterns. The team also configured the firewall to verify the source IP addresses of incoming ICMP packets, so it can catch packets sent from spoofed addresses.

## Respond

The incident management team responded to the security event by blocking incoming ICMP packets and stopping all non-critical network services.

For future security events, the cybersecurity team will also contain the incident by isolating affected systems so the disruption doesn't spread across the network. Once the incident is contained and neutralized, the team will analyze the network logs for details that can help it protect against similar security events in the future.

The network security team will receive updated training on firewall maintenance procedures to ensure they do not leave any firewalls unconfigured in the future. The team will also be trained on how best to handle and recover from similar DoS attacks, using log data captured during this incident.

Upper management will be informed of this event and will notify law enforcement and any other organizations as required by law.

## Recover

Once the incident management team blocked incoming ICMP packets and stopped all non-critical network services, they proceeded to restore critical network services.

The network security team will also investigate whether the incident damaged or corrupted any data in the internal network database. If it did, the team will restore the affected data from the most recent backup.

If another ICMP flood attack happens, the team will recover in this order: block the incoming ICMP traffic at the firewall, take all non-critical network services offline to reduce internal network traffic, restore critical network services first, and then bring all non-critical network systems and services back online once the flood of ICMP packets has stopped.
