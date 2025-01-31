# Wireshark TLS Handshake Data - `yusufasik.com`

This repository contains a JSON file generated from Wireshark capturing TLS handshake data for HTTP/HTTPS requests where the `Server Name Indication (SNI)` matches `"yusufasik.com"`. 

## Overview

The captured data includes detailed information about the SSL/TLS handshake process for requests that reference the domain `yusufasik.com`. This JSON file contains all relevant information regarding the server's public key, cipher suites, and other key aspects of the SSL/TLS connection setup.

## File Structure

The JSON file consists of the following data:

- **Source and Destination IP**: The IP addresses involved in the connection.
- **TLS Handshake Information**: Details about the TLS handshake, including protocol versions, cipher suites, and extensions.
- **Server Name Indication (SNI)**: The domain name (`yusufasik.com`) used during the handshake.
- **Session Keys**: Information related to the session setup (if decrypted or relevant).
  
## Purpose

The purpose of this file is to provide a record of TLS handshakes for the domain `yusufasik.com`, which can be useful for:

- **Security analysis**: Inspecting how the TLS handshake is conducted for this domain and whether there are any security concerns.
- **Network troubleshooting**: Understanding the communication process and identifying potential issues with HTTPS connections.
- **Compliance and auditing**: Ensuring the domain is using secure protocols and certificates for encrypted communication.

## How to Use

To view the data:

1. Open the JSON file in any JSON viewer or text editor.
2. Examine the details of the TLS handshake, focusing on the fields related to the `SNI` and cipher suites.
3. Use the file for further analysis of SSL/TLS handshake security or to investigate specific network requests involving the domain `yusufasik.com`.

### Example of a Typical Entry

```json
{
  "frame_number": 1,
  "timestamp": "2025-01-30T12:34:56.789",
  "source_ip": "192.168.1.10",
  "destination_ip": "93.184.216.34",
  "tls_handshake": {
    "protocol_version": "TLS 1.2",
    "cipher_suite": "TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256",
    "extensions": {
      "server_name": "yusufasik.com"
    }
  }
}
```

## How to Generate the File
The JSON file was generated using Wireshark with the following filter applied:

```sql
tls.handshake.extensions_server_name contains "yusufasik.com"
```

## Steps for generating the file:

- **Capture Traffic**: Use Wireshark to capture network traffic on the desired network interface.
- **Apply the Filter**: Apply the filter tls.handshake.extensions_server_name contains "yusufasik.com" to capture only traffic related to the yusufasik.com domain.
- **Export to JSON**: Export the filtered packet capture to a JSON file format.
- **Save the File**: Store the file for later analysis or reporting.

## Tools Used
- **Wireshark**: Network protocol analyzer for capturing the TLS handshake and generating the JSON file.
- **JSON**: Standard data format used for storing and exchanging structured information.

## License
This project is licensed under the [Apache License](LICENSE) 

## Contributing

If you would like to contribute to this repository:

1. Fork the repository.
2. Make your changes or add new accessibility testing results.
3. Submit a pull request for review.

---

For questions or suggestions, feel free to create an issue in this repository.
