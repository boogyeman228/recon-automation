#!/bin/bash

required_tools=("docker" "amass" "assetfinder" "httprobe" "gowitness")
echo "[*] Checking dependencies..."
for tool in "${required_tools[@]}"; do
    if ! command -v $tool &> /dev/null; then
        echo "[!] $tool is not installed."

        case $tool in
            docker)
                echo "    >> Try: sudo apt install docker.io"
                ;;
            amass)
                echo "    >> Try: sudo snap install amass"
                ;;
            assetfinder)
                echo "    >> Try: go install github.com/tomnomnom/assetfinder@latest"
                ;;
            httprobe)
                echo "    >> Try: go install github.com/tomnomnom/httprobe@latest"
                ;;
            gowitness)
                echo "    >> Try: go install github.com/sensepost/gowitness@latest"
                ;;
        esac

        echo "[x] Exiting because $tool is missing."
        exit 1
    else
        echo "[+] $tool is installed."
    fi
done

read -p "Enter target domain (e.g. example.com): " url
./code "$url"
