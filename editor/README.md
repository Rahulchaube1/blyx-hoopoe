# Blyx Hoopoe

Plan a thumbnail and check the decoded pixel buffer against a byte budget.

This extension includes the Blyx Hoopoe 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

1. Open an empty file named `hoopoe-demo.blyx`.
2. Type `blyx-hoopoe-demo` and select **Hoopoe — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
100
50
300
15000
0
```

## Use Hoopoe in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/hoopoe`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-hoopoe-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-hoopoe-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/hoopoe) · [Framework source](https://github.com/Rahulchaube1/blyx-hoopoe/tree/977d385cadc36c8f3ccabbc8cde1bf108cc30af4) · [Report an issue](https://github.com/Rahulchaube1/blyx-hoopoe/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
