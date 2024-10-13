# Cloudflare Worker Adapter

This is a lightweight Cloudflare Workers adapter that enables projects to run independently without requiring the Cloudflare platform. It provides core features like:

- Parsing of TOML configuration files
- Support for multiple KV Namespace implementations
- Fetch API with proxy capabilities

## Installation

To add the package to your project, simply run:

```bash
npm install cloudflare-worker-adapter --save

Usage Example
typescript
Copy code
const configuration: Config = {
    port: 8787, // The port on which the server will run
    hostname: '0.0.0.0', // The host address to bind the server to
    options: {
        DATABASE: cache, // Cloudflare Worker bindings
    },
    config: './test/wrangler.toml', // The path to your wrangler.toml configuration file
    setting: {
        baseURL: 'https://example.com', // The base URL for outgoing fetch requests
    },
};

// Customize this logic as per your requirements
async function handleRequest(req: Request) {
    console.log('Incoming Request:', req.url);
    return await fetch('https://example.com/users/godleader');
}

// Initialize the server with the given configuration
startServer(configuration.port, configuration.hostname, configuration.config, configuration.options, configuration.setting, handleRequest);
```

Overview
The purpose of this project is to offer a simple Cloudflare Workers runtime, particularly for the AITG Bot or similar projects that need to operate independently of the Cloudflare platform. It provides basic functionality for integrating Cloudflare Worker features into any environment. More features will be introduced in the future to expand its capabilities. For additional details, refer to the AITG Bot project.

License
The Cloudflare Worker Adapter is available under the MIT License. Check out the LICENSE for more information.
