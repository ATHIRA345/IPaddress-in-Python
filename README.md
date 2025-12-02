📘 Python ipaddress Module – Complete Guide with Examples

The ipaddress module in Python provides an easy and powerful way to work with IPv4 and IPv6 addresses.
It supports validation, comparison, subnet calculations, and membership checking.

This guide contains full explanations and working Python programs for your GitHub project.

🚀 Introduction
Python’s ipaddress module is part of the standard library (Python 3.3+).
It allows you to:

Validate IP addresses

Compare two IPs

Calculate difference between IP addresses

Check if an IP belongs to a network

Perform subnetting operations

Import it using:

import ipaddress
📂 Table of Contents

Validating IP Addresses

Comparing Two IPs

Difference Between IP Addresses

Check if IP Belongs to Network

Subnet Operations

Full Example Programs

Summary

🧪 1. Validating IP Addresses

You can verify whether a string is a valid IPv4/IPv6 address using ip_address().

Example
import ipaddress

ip = "192.168.1.300"

try:
    addr = ipaddress.ip_address(ip)
    print(f"{addr} is a valid IP address")
except ValueError:
    print(f"{ip} is NOT valid")

Output
192.168.1.300 is NOT valid

🔍 2. Comparing Two IPs

IP objects can be compared using <, >, and ==.

Example Program
import ipaddress

ip1 = ipaddress.ip_address("192.168.1.10")
ip2 = ipaddress.ip_address("192.168.1.25")

print("IP 1:", ip1)
print("IP 2:", ip2)

if ip1 < ip2:
    print(f"{ip1} comes before {ip2}")
elif ip1 > ip2:
    print(f"{ip1} comes after {ip2}")
else:
    print("Both IPs are equal")

Output
192.168.1.10 comes before 192.168.1.25

🔢 3. Difference Between Two IP Addresses

Convert IPs to integers to calculate difference.

Example Program
import ipaddress

ip1 = ipaddress.ip_address("192.168.1.10")
ip2 = ipaddress.ip_address("192.168.1.40")

difference = int(ip2) - int(ip1)

print(f"Difference between {ip1} and {ip2}: {difference} addresses")

Output
Difference between 192.168.1.10 and 192.168.1.40: 30 addresses

🌐 4. Check if IP Belongs to a Network

Use ip_network() and in operator.

Example
import ipaddress

network = ipaddress.ip_network("192.168.1.0/24")
ip = ipaddress.ip_address("192.168.1.50")

if ip in network:
    print(f"{ip} belongs to {network}")
else:
    print(f"{ip} does NOT belong to {network}")

Output
192.168.1.50 belongs to 192.168.1.0/24

🧩 5. Subnetting Operations

You can easily divide networks into smaller subnets.

Example
import ipaddress

network = ipaddress.ip_network("10.0.0.0/16")

print("Subnets of 10.0.0.0/16 (/24):")
for subnet in network.subnets(prefixlen_diff=8):
    print(subnet)

🧑‍💻 6. Full Example Programs

Below are complete ready-to-run scripts.

compare_ips.py
import ipaddress

ip1 = ipaddress.ip_address("192.168.1.10")
ip2 = ipaddress.ip_address("192.168.1.25")

print("IP 1:", ip1)
print("IP 2:", ip2)

if ip1 < ip2:
    print(f"{ip1} comes before {ip2}")
elif ip1 > ip2:
    print(f"{ip1} comes after {ip2}")
else:
    print("Both IPs are equal")

validate_ip.py
import ipaddress

ip = input("Enter an IP: ")

try:
    addr = ipaddress.ip_address(ip)
    print(f"{addr} is valid")
except ValueError:
    print(f"{ip} is NOT a valid IP")

ip_difference.py
import ipaddress

ip1 = ipaddress.ip_address("192.168.1.10")
ip2 = ipaddress.ip_address("192.168.1.40")

difference = int(ip2) - int(ip1)

print("IP difference:", difference)

network_membership.py
import ipaddress

network = ipaddress.ip_network("192.168.1.0/24")
ip = ipaddress.ip_address("192.168.1.60")

print(ip in network)

subnet_operations.py
import ipaddress

network = ipaddress.ip_network("10.0.0.0/24")

print("Subnets:")
for subnet in network.subnets(prefixlen_diff=2):
    print(subnet)

🏁 7. Summary

This guide covered:

Feature	Included
IP validation	✔
Comparing IPs	✔
IP difference	✔
Network membership	✔
Subnetting	✔
Full example scripts	✔

The ipaddress module is powerful and simple, making it ideal for networking tasks in Python.
