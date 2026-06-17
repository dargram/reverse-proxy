# 🔀 Reverse Proxy

A lightweight reverse proxy built with **Quart** and **httpx** that forwards requests to a target site defined in `config.json`, with partial data encryption.

## Features

- Forwards all incoming requests to a configured target site
- Partial encryption of transmitted data
- Simple configuration via `config.json`
- Easy one-command startup

## Requirements

- Python 3.8+
- [Quart](https://quart.palletsprojects.com/)
- [httpx](https://www.python-httpx.org/)

Install dependencies:

```bash
pip install quart httpx
```

## Configuration

Edit `config.json` to set your target site:

```json
{
  "target": "https://example.com"
}
```

## Usage

Start the proxy with either of these commands:

```bash
./start
```

or

```bash
bash start
```

The proxy will begin forwarding all incoming requests to the target defined in your config.

## How It Works

```
Client → Reverse Proxy (Quart + httpx) → Target Site
                  ↕
           Partial encryption
```

1. Client sends a request to the proxy
2. The proxy (partially) encrypts the data
3. The request is forwarded to the configured target site
4. The response is returned back to the client

## Project Structure

```
reverse-proxy/
├── start           # Startup script
├── config.json     # Target site configuration
└── ...
```

## License

MIT
