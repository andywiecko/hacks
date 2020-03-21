# hacks


## collection of useful Linux hacks

* Merging two pdf documents (with hyperlink working), requirements: `pdftk`
```
pdftk file1.pdf file2.pdf cat output mergedfile.pdf
```

* Spliting pdf files (pages range)
```
pdftk file.pdf cat 12-15 output file_p12-15.pdf
```

* Omit repeated lines
```
uniq filename.txt
```
or using `sort` with `-u` flag
```
sort -u filename.txt
```

* SVG to PDF conversion, requirements: `librsvg2-bin`
```
rsvg-convert -f pdf -o fig1.pdf fig1.svg
```

* `sponge` -- soak up standard input and write to a file, requirements: `moreutils`
```
sort -g -k1 -k2 file | sponge file
```

* reduce video size, requirements: `ffmpeg`
```
ffmpeg -i input.mp4 -fs 100KB output.mp4
```

* grep from `text` to the first empty line
```
awk '/text/,/^$/' filename.txt
```

* write empty line every n-lines
```
awk -v n=5 '1; NR % n == 0 {print ""}' filename.txt
```

* export `code` installed extensions
```
code --list-extensions | xargs -L 1 echo code --install-extension
```
