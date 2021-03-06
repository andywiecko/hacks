# hacks

## collection of useful Linux hacks

- Merging two pdf documents (with hyperlink working), requirements: `pdftk`

```
pdftk file1.pdf file2.pdf cat output mergedfile.pdf
```

- Merging two pdf (simpler then pdftk)

```
pdfunite page1.pdf page2.pdf out.pdf
```

- Spliting pdf files (pages range)

```
pdftk file.pdf cat 12-15 output file_p12-15.pdf
```

- Omit repeated lines

```
uniq filename.txt
```

or using `sort` with `-u` flag

```
sort -u filename.txt
```

- SVG to PDF conversion, requirements: `librsvg2-bin`

```
rsvg-convert -f pdf -o fig1.pdf fig1.svg
```

- `sponge` -- soak up standard input and write to a file, requirements: `moreutils`

```
sort -g -k1 -k2 file | sponge file
```

- reduce video size, requirements: `ffmpeg`

```
ffmpeg -i input.mp4 -fs 100KB output.mp4
```

- grep from `text` to the first empty line

```
awk '/text/,/^$/' filename.txt
```

- write empty line every n-lines

```
awk -v n=5 '1; NR % n == 0 {print ""}' filename.txt
```

- skip first `10` lines

```
tail -n +10 filename.txt
```

- export `code` installed extensions

```
code --list-extensions | xargs -L 1 echo code --install-extension
```

## collection of useful `git` related hacks

- pack `git` current branch into archive

```
git archive --output=./develop-11-02-2021.zip --format=zip HEAD
```

- remove all local branches (except `develop`)

```
git branch | grep -v develop | xargs git branch -D
```

## collection of useful Windows hacks

- disc format 
   - open <kbd> Win + R </kbd> and type `diskpart` and run with admin privileges
   - then to format disc 1, type in console:
```
list disk
select disk 1
clean
```

## collection of useful `inkscape` hacks

- ungroup `Shift+Ctrl+G`
- group `Ctrl+G`
- unlink clone `Shift+Alt+D` ("ungrouping ungroupinglable")
- document canvas `Shift+Ctrl+D`
