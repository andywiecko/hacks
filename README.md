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
