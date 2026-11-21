## Check a thumbnail buffer before allocation

Returns [output width, output height, aligned stride, bytes, fits budget]. Includes one output buffer with one byte per channel. Decoder and encoder overhead are outside this estimate. Invalid arguments and nonfinite results return an empty vector.

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

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-hoopoe)
