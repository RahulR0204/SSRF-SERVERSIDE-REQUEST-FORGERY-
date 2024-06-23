# SSRF-SERVERSIDE-REQUEST-FORGERY-

This repository provides information on Server-Side Request Forgery (SSRF) vulnerabilities, including examples of different types of SSRF attacks and preventive measures to secure applications against such threats.

## SSRF Vulnerability Examples and Mitigation

It allows an attacker to make requests from a vulnerable server. The target server can be tricked into making HTTP requests to an arbitrary domain that supports data imports from URLs or allows them to read data from URLs.
URLs can be manipulated, either by replacing them with new ones or by tampering with URL path traversal.

**Git URL:**
[https://github.com/paulveillard/cybersecurity-ssrf.git](https://github.com/paulveillard/cybersecurity-ssrf.git)

## Types of SSRF

### 1. Blind SSRF
Blind SSRF occurs when the attacker cannot see the response of the SSRF request but can infer information based on side effects, such as DNS lookups or error messages. To exploit this type of SSRF we have to feed URL followed by the colon and port number, by observing responses and error messages from the server we can find the open and close ports of the server. 

**Example:**
```
http://example.com:1337
http://example.com:9923
```

### 2. Partial SSRF
Partial (SSRF) Is a vulnerability where the attacker can influence only a part of the server's request. Unlike a full SSRF, partial SSRF gives the attacker limited control, typically over certain segments of the URL, such as the path, query string, or specific parameters.

**Example URLs:**
```
file:///etc/hosts
file:///etc/config
```

### 3. Full Response SSRF
In Full SSRF we have complete control over the access and the services running on the internal network and can few can find out the vulnerabilities in it. In this type of SSRF

We can use protocols like file://,dict://,http:// etc. Full SSRF vulnerability may cause the application crash through buffer overflow that is by sending large string request. 

**Example URL:**
```
http://192.168.1.8/BBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBB
```

## Preventive Measures

### 1. Whitelisting
Server only allows a few domain name to be used in the request, serve has a white list of domain names, if the domain name from that list matches with domain name from request server declines the request
### 2. Blacklisting
Server discards all the request containing IP address, domain names, keywords from the blacklist of server.
### 3. Restricted Content
Server allows to access only particular amount of files to user, it allows only the few file extensions types for public areas.

## Repository Content

- **Examples/**: Various SSRF payload examples.
- **Mitigations/**: Code snippets and configurations to prevent SSRF.
- **Documentation/**: Detailed explanations of SSRF types and prevention techniques.

## Usage

Clone the repository:
```bash
git clone https://github.com/paulveillard/cybersecurity-ssrf.git
```

Navigate to the directory:
```bash
cd cybersecurity-ssrf
```

Explore the examples and mitigation strategies to understand and defend against SSRF vulnerabilities.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
