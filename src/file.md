# ファイル

| Recipe | Crates | Categories |
|--------|--------|------------|
| [ファイルから文字列の行を読み取る][ex-std-read-lines] | [![std-badge]][std] | [![cat-filesystem-badge]][cat-filesystem] |
| [同一ファイルの読み書きを避ける][ex-avoid-read-write] | [![same_file-badge]][same_file] | [![cat-filesystem-badge]][cat-filesystem] |
| [メモリマップを使ってランダムにファイルにアクセする][ex-random-file-access] | [![memmap-badge]][memmap] | [![cat-filesystem-badge]][cat-filesystem] |
| [過去24時間以内に変更されたファイル名][ex-file-24-hours-modified] | [![std-badge]][std] | [![cat-filesystem-badge]][cat-filesystem] [![cat-os-badge]][cat-os] |
| [与えられたパスをループして探す][ex-find-file-loops] | [![same_file-badge]][same_file] | [![cat-filesystem-badge]][cat-filesystem] |
| [重複したファイル名を再帰的に探す][ex-dedup-filenames] | [![walkdir-badge]][walkdir] | [![cat-filesystem-badge]][cat-filesystem] |
| [与えられた値のファイルを再帰的に探す][ex-file-predicate] | [![walkdir-badge]][walkdir] | [![cat-filesystem-badge]][cat-filesystem] |
| [ドットファイルをスキップしながらディレクトリを走査する][ex-file-skip-dot] | [![walkdir-badge]][walkdir] | [![cat-filesystem-badge]][cat-filesystem] |
| [与えられた深さで再帰的にファイルサイズを計算する][ex-file-sizes] | [![walkdir-badge]][walkdir] | [![cat-filesystem-badge]][cat-filesystem] |
| [全てのpngファイルを再帰的に探す][ex-glob-recursive] | [![glob-badge]][glob] | [![cat-filesystem-badge]][cat-filesystem] |
| [ファイル名の大文字小文字を無視して、指定されたパターンを持つすべてのファイルを検索する][ex-glob-with] | [![glob-badge]][glob] | [![cat-filesystem-badge]][cat-filesystem] |

[ex-std-read-lines]: file/read-write.html#read-lines-of-strings-from-a-file
[ex-avoid-read-write]: file/read-write.html#avoid-writing-and-reading-from-a-same-file
[ex-random-file-access]: file/read-write.html#access-a-file-randomly-using-a-memory-map
[ex-file-24-hours-modified]: file/dir.html#file-names-that-have-been-modified-in-the-last-24-hours
[ex-find-file-loops]: file/dir.html#find-loops-for-a-given-path
[ex-dedup-filenames]: file/dir.html#recursively-find-duplicate-file-names
[ex-file-predicate]: file/dir.html#recursively-find-all-files-with-given-predicate
[ex-file-skip-dot]: file/dir.html#traverse-directories-while-skipping-dotfiles
[ex-file-sizes]: file/dir.html#recursively-calculate-file-sizes-at-given-depth
[ex-glob-recursive]: file/dir.html#find-all-png-files-recursively
[ex-glob-with]: file/dir.html#find-all-files-with-given-pattern-ignoring-filename-case

{{#include links.md}}
