<img src="assets/logo.png" width="112" height="112" alt="Hoopoe logo">

# Hoopoe

Plan a thumbnail and check the decoded pixel buffer against a byte budget. This Blyx workflow framework is part of the documents, images and media collection.

Encoded file size gives a poor estimate of decoded thumbnail memory. Account for output dimensions and scanline padding before allocating. [Pillow, aspect-preserving containment](https://pillow.readthedocs.io/en/stable/reference/ImageOps.html#PIL.ImageOps.contain)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-hoopoe.git
cd blyx-hoopoe
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-hoopoe) · [Package page](https://www.blyx-lang.space/packages/hoopoe) · [Handbook](https://doc.blyx-lang.space/guide/hoopoe)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-hoopoe.git vendor/hoopoe
```

```blyx
use vendor::hoopoe::hoopoe;

fn main() {
    let width = 400.0;
    let height = 200.0;
    let box_w = 100.0;
    let box_h = 100.0;
    let channels = 3.0;
    let align = 4.0;
    let memory = 14000.0;
    let result = hoopoe_thumbnail(width, height, box_w, box_h, channels, align, memory);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
100
50
300
15000
0
```

## API

`hoopoe_thumbnail(width, height, box_w, box_h, channels, align, memory)`

Returns [output width, output height, aligned stride, bytes, fits budget]. Includes one output buffer with one byte per channel. Decoder and encoder overhead are outside this estimate. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| width | A positive exact integer |
| height | A positive exact integer |
| box_w | A positive exact integer |
| box_h | A positive exact integer |
| channels | A positive exact integer |
| align | A positive exact integer |
| memory | A nonnegative exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- 400 200 100 100 3 4 14000
```

## Libraries

- [AspectFit](https://github.com/Rahulchaube1/blyx-aspectfit/tree/v0.1.0) — Fit an image inside a box while preserving aspect ratio.
- [RasterBytes](https://github.com/Rahulchaube1/blyx-rasterbytes/tree/v0.1.0) — Estimate uncompressed raster storage with aligned scanlines.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-hoopoe/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The package artwork uses [Lucide icons](https://lucide.dev/license); see [artwork notices](assets/NOTICE.txt).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
