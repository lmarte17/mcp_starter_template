# MCP Starter Template

A starter template for building Model Context Protocol (MCP) servers. This template provides the basic structure and boilerplate code needed to create custom MCP tools that can be integrated with AI assistants like Claude.

## What is MCP?

The Model Context Protocol (MCP) allows AI assistants to interact with external tools and services. Using this template, you can build servers that expose custom functionality to AI models, enabling them to perform actions like:

- Fetching data from APIs
- Performing calculations
- Accessing databases
- Controlling external systems
- And much more!

## Prerequisites

- Node.js (v18 or later recommended)
- npm or yarn

## Getting Started

1. Clone this repository to use as a starting point:

```bash
git clone https://github.com/your-username/mcp-starter-template.git
cd mcp-starter-template
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Build the TypeScript code:

```bash
npm run build
# or
yarn build
```

4. Run the server:

```bash
npm start
# or
yarn start
```

## Project Structure

- `src/index.ts` - The main entry point for your MCP server
- `src/` - Directory for your server's source code
- `dist/` - Output directory for compiled code (created after building)

## Creating Your Own Tools

The template includes an example tool to help you get started. To create your own tools:

1. Open `src/index.ts`
2. Locate the tools section (marked with comments)
3. Add your own tool definitions following the example pattern:

```typescript
server.tool(
  "your_tool_name", 
  "Description of what your tool does", 
  {
    // Define parameters with zod schemas
    param1: z.string().describe("Description of parameter 1"),
    param2: z.number().describe("Description of parameter 2")
  },
  async ({ param1, param2 }) => {
    // Implement your tool logic here
    
    // Return results according to MCP protocol
    return {
      content: [
        {
          type: "text", 
          text: "Your result output here"
        }
      ]
    };
  }
);
```

## Building and Testing

After making changes to your code, you need to rebuild the project:

```bash
npm run build
# or
yarn build
```

This will compile the TypeScript code into JavaScript in the `dist/` directory.

## Connecting to AI Assistants

MCP servers can be used with compatible AI assistants. To connect your server:

1. Run your server locally
2. Set up the appropriate configuration in your AI assistant's interface
3. Use the MCP protocol to communicate between the assistant and your server

## Tips for Development

- Use TypeScript interfaces to define your API response types
- Leverage the `makeApiRequest` helper function for external API calls
- Structure your tools to be reusable and composable
- Use proper error handling for robust operation

## Resources

- [MCP Documentation](https://github.com/anthropics/model-context-protocol) - Official MCP documentation
- [Zod Documentation](https://github.com/colinhacks/zod) - For schema validation
- [TypeScript Documentation](https://www.typescriptlang.org/docs/) - For TypeScript references

## License

[MIT License](LICENSE)
