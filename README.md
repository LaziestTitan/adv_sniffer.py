Feature-rich, multi-threaded Python 3 sniffer that goes far beyond the minimal example.
It adds:

    Layer-7 payload carving (HTTP, DNS, SMTP, FTP, POP, IMAP)
    TCP stream re-assembly (bidirectional) with finite-state tracking
    IP de-fragmentation & out-of-order segment handling
    Automatic PCAP rotation + live JSON/CSV export
    BPF & display-filter syntax support
    CLI (argparse) + graceful CTRL-C shutdown
    Extensible plugin architecture – drop a .py file into plugins/ and it is auto-loaded

The code is 100 % self-contained except for two PyPI packages:

Dependancies are; 
sudo python3 -m pip install scapy scapy-http  # scapy-http gives Request/Response layers

sudo python3 adv_sniffer.py -i eth0 -f "tcp port 80 or 53" \
                            --reassemble --export json \
                            --rotate 100                # MB per PCAP
