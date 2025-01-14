## パスからプレフィックスを削除しながらのtarの解凍

[![flate2-badge]][flate2] [![tar-badge]][tar] [![cat-compression-badge]][cat-compression]

[`Archive::entries`]を使いイテレートする。指定したパスプレフィックス(`bundle/logs`)を削除するには[`Path::strip_prefix`]を使ってください。最後に[`Entry::unpack`]で[`tar::Entry`]を抽出します。

```rust,no_run
# #[macro_use]
# extern crate error_chain;
extern crate flate2;
extern crate tar;

use std::fs::File;
use std::path::PathBuf;
use flate2::read::GzDecoder;
use tar::Archive;
# 
# error_chain! {
#   foreign_links {
#     Io(std::io::Error);
#     StripPrefixError(::std::path::StripPrefixError);
#   }
# }

fn main() -> Result<()> {
    let file = File::open("archive.tar.gz")?;
    let mut archive = Archive::new(GzDecoder::new(file));
    let prefix = "bundle/logs";

    println!("Extracted the following files:");
    archive
        .entries()?
        .filter_map(|e| e.ok())
        .map(|mut entry| -> Result<PathBuf> {
            let path = entry.path()?.strip_prefix(prefix)?.to_owned();
            entry.unpack(&path)?;
            Ok(path)
        })
        .filter_map(|e| e.ok())
        .for_each(|x| println!("> {}", x.display()));

    Ok(())
}
```

[`Archive::entries`]: https://docs.rs/tar/*/tar/struct.Archive.html#method.entries
[`Entry::unpack`]: https://docs.rs/tar/*/tar/struct.Entry.html#method.unpack
[`Path::strip_prefix`]: https://doc.rust-lang.org/std/path/struct.Path.html#method.strip_prefix
[`tar::Entry`]: https://docs.rs/tar/*/tar/struct.Entry.html
