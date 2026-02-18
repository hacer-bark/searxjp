# About SearXJP

SearXJP is a privacy-hardened, Asia-optimized instance of the [SearXNG] metasearch engine.

Unlike standard public instances, SearXJP is built upon a **Split-Knowledge Architecture**. We prioritize two things: low-latency access for users in Japan/Asia, and a physical separation between the server that knows *who* you are and the server that knows *what* you are searching for.

## Our Architecture: The "Split-Knowledge" Model

To compromise your privacy on SearXJP, an adversary would need to simultaneously breach two different servers, in two different legal jurisdictions, owned by different providers.

We operate a strict **Two-Node Policy**:

### 1. 🇯🇵 The Entry Node (Tokyo, Japan)
This is the server you connect to. It acts strictly as a **TCP Blind Relay**.
*   **What it knows:** It knows your IP address.
*   **What it DOES NOT know:** It **cannot** see your search query.
*   **How it works:** This server forwards encrypted SSL packets directly to our backend. It does not hold the SSL keys, meaning it is mathematically impossible for this server to decrypt or read your traffic.

### 2. 🌏 The Processing Node (Undisclosed Location)
This server receives the traffic from the Japan Entry Node via an encrypted private tunnel.
*   **What it knows:** It decrypts the traffic and knows what you are searching for.
*   **What it DOES NOT know:** It **cannot** see your IP address. It only sees the internal IP of the Japan Entry Node.
*   **How it works:** This node handles the computation, aggregates results from Google/Bing/DuckDuckGo, and sanitizes the data before sending it back through the tunnel.

## Network Performance & China Accessibility

Our Entry Node in Tokyo utilizes a premium BGP network mix, including **GSL, PCCW, COGENT, EIE, and JPNAP**.

**For users in Mainland China:**
While we have not officially tested accessibility through the Great Firewall and cannot guarantee availability, our network infrastructure is technically optimized for cross-border connectivity. The inclusion of **PCCW** and other premium Asian routes theoretically offers superior latency and stability compared to connecting to US or European instances.

## Transparency: Logging & Data Retention

We believe in radical transparency regarding what we log and, more importantly, what we *cannot* log.

### Standard Internet Connections (Clearweb)
*   **On the Japan Entry Node:** We maintain a rolling **15-minute TCP connection log**.
    *   *Why?* This is strictly for DDoS protection and Rate Limiting. If an IP floods us with connections, the firewall blocks it.
    *   *Privacy:* Because this node only processes encrypted TCP streams, **it is impossible for these logs to contain your search queries.**
*   **On the Processing Node:** **No Logs.**
    *   We do not log IP addresses (we don't see them).
    *   We do not log search queries.
    *   Rate limiting is applied based on the *route* (e.g., "Global Traffic"), not by user IP.

### Tor & I2P Connections
*   **Strict No-Logs Policy:** Traffic coming via Tor or I2P bypasses the standard TCP rate limiter logs entirely.
*   We do not track entry timing, correlation data, or connection metadata for anonymity networks.

## How to set as default

SearXJP supports [OpenSearch]. You can add it to your browser easily:

- [Firefox] - Right-click the address bar and select "Add SearXJP".
- [Chromium]-based browsers (Chrome, Brave, Edge) - Go to Settings > Search Engine > Manage Search Engines and add SearXJP manually if it does not appear automatically.

[SearXNG]: https://github.com/searxng/searxng
[OpenSearch]: https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md
[Firefox]: https://support.mozilla.org/en-US/kb/add-or-remove-search-engine-firefox
[Chromium]: https://www.chromium.org/tab-to-search
