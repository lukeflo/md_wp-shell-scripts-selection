# Shell Script Selection for Markdown-Files

Here i share some of my small Shell-scripts which i use to automate reccuring processes.

To run the files they should be copied to a directory included in your `$PATH`. Afterwards, it is necessary to make them executable. On my Arch-based Linux-system i use the following commands (from the location of the downloaded/cloned script-file):

~~~shell
$ cp [script-name] ~/.local/bin && cd ~/.local/bin
$ chmod 755 [script-name]
~~~

On other Linux-distributions, MacOS or Windows with subsystem for Linux you may need another directory which is included in your `$PATH` or actively include one.

## main-index script

The script `main-index` is used to create an index of a workspace containing multiple subfolders with Markdown files using Wikilinks. Therefore you need an Programm, Plugin or Extension for your editor which enables Markdown-notes with Wikilinks. I use the the [Foam-Extension](https://open-vsx.org/extension/foam/foam-vscode) for VScode respectively VScodium – works very good. Other options are the [Markdown-Notes Extension](https://open-vsx.org/extension/kortina/vscode-markdown-notes) or a stand-alone programm like [Zettlr](https://www.zettlr.com/).

To use the script you only need to run it with an optional argument. The argument defines the name of the index-file (without file-extension!). If it is left blank, the file will be named "index":

    main-index [name-of-index-file]

## automdindex

Is the same like the `main-index` script, but only works in the current directory and doesn't search subdirectories recursivley.

    automdindex [name-of-index-file]

## pandoc-with-bib

Is a shortened command for converting files with `pandoc`. It will convert file-formats using pandoc and creating a bibliography using *Biblatex*, *CSL-citation-styles* and *citeproc*.

You can pass two or three arguments. The first is the input-file, the second the output-file (both **with** file-extensions), and the last defines the csl-citation-style (just the filename **without** .csl extension). If the third is left blank, the sript uses APA as standard if it is downloaded already:

    pandoc-with-bib [input-file] [output-file] [citation-style]

In order for it to run without errors, the directory paths to the bibliography and citation styles must first be defined in the script file. Look in the comments there.

# License

All scripts are licensed under [GNU GPLv3](https://github.com/lukeflo/md_wp-shell-scripts-selection/blob/main/LICENSE.md).
These programms come with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to redistribute it
under certain conditions.
