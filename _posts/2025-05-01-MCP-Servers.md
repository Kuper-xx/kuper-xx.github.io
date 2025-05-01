---
title: MCP Servers
published: true
---

[Link to index page](/).

<h1 align="center">
    <img src="https://i.redd.it/bdgcnrnzsmte1.png" alt="mcp-servers" width="600px">
</h1>

### [](#header-1)Introduction to MCP Servers

MCP (Model Completion Protocol) Servers are powerful extensions for Claude that allow it to interact with your computer. It is like an USB for AI LLM Models. There are two examples: 
* **Filesystem**: which handles files and directories. 
* **Playground**: which enables browser automation and interactive tools. Let's learn how to use them!

## [](#header-2)First step - Setup

Setting up MCP Servers is surprisingly simple:

1. **Install Claude Desktop app**
   - Download and install from Anthropic's website
   - Login with your account

2. **Enable MCP Servers**
   - Go to Settings
   - Navigate to Advanced Options
   - Toggle on "Enable MCP Server"
   - Restart Claude


## [](#header-2)Second step - Using Filesystem MCP

The Filesystem MCP lets Claude read and write files on your computer. You just have to modify the config the claude_desktop_config.json file and restart Claude:

```
{
  "mcpServers": {
    "filesystem": {
          "command": "npx",
          "args": [
            "-y",
            "@modelcontextprotocol/server-filesystem",
            "C:\\Users\\User\\Desktop",
            "C:\\path\\to\\other\\allowed\\dir"
          ]
    }
  }
}
```

### [](#header-3)Example: A Simple File Manager

Here's a quick example of how to use Claude to manage your files:

1. Ask Claude: "Can you list all the files in my Documents folder?"
2. Claude will use `list_directory` to show your files
3. Ask Claude: "Create a new text file called notes.txt with a list of my tasks"
4. Claude will create the file with `write_file`

## [](#header-2)Third step - Using Playground MCP

Playground MCP lets Claude control your web browser. Here are the basics, just add it like this to the same file:

```
{
  "mcpServers": {
    "filesystem": {
          "command": "npx",
          "args": [
            "-y",
            "@modelcontextprotocol/server-filesystem",
            "C:\\Users\\User\\Desktop",
            "C:\\path\\to\\other\\allowed\\dir"
          ]
    },
    "playwright": {
                "command":"npx",
                "args":["@playwright/mcp@latest", "--browser", "msedge"]
    }
  }
}
```

In my example I use msedge.exe browser...

### [](#header-3)Example: Web Research Assistant

Here's how to use Claude as a research assistant:

1. Ask Claude: "Can you search for information about climate change?"
2. Claude will navigate to search engines using `browser_navigate`
3. Claude will read the content using `browser_snapshot`
4. Claude will summarize the information for you

## [](#header-2)Putting it all together

The real power comes when combining both MCP types. For example:

1. Use Playground MCP to browse the web and find data
2. Use Filesystem MCP to save that data to a file
3. Ask Claude to analyze the data and create a report
4. Save the report as a file using Filesystem MCP again

### [](#header-3)Tips for Success

- Be specific when asking Claude to use MCP tools
- Start simple and build up to more complex workflows
- Remember that Claude needs permission to access files and websites
- Use the correct paths for your operating system

That's it! With these basics, you can now leverage the power of MCP Servers to make Claude even more helpful in your daily tasks.
