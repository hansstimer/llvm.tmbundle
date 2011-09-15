#LLVM TextMate Bundle

This is a TextMate Bundle for viewing and editing [LLVM](http://llvm.org/) (Low Level Virtual Machine) assembly files (.ll).

# Installation

For background on installing TextMate Bundles read [Installing a Bundle](http://manual.macromates.com/en/bundles#installing_a_bundle).

## Install Location

If you plan on making changes to the Bundle that you want me to pickup, you must install in a different location than you would typically install TextMate Bundles. If you use the TextMate Bundle editor to edit a bundle in any location other than `~/Library/Application Support/TextMate/Bundles`, it will create delta files which are very difficult to merge.

### Normal Install

	cd ~/Library/Application\ Support/TextMate/Pristine\ Copy/Bundles
	git clone git@github.com:hansstimer/llvm.tmbundle.git 
	osascript -e 'tell app "TextMate" to reload bundles'

### Development Install

	cd ~/Library/Application Support/TextMate/Bundles
	git clone git@github.com:hansstimer/llvm.tmbundle.git 
	osascript -e 'tell app "TextMate" to reload bundles'

### Non TextMate Install

There are other editors that have some level of TextMate Bundle compatibility:

* Sublime Text 2
* Vico
* VIM (with SnipMate plugin)
* and many more

Please see the documentation for your editor as to where to put the files. Not all Bundle features will work with all editors, however most editors support TextMate snippet files now days.

## Use

These are the snippets implemented:

Instruction | Short Cut
---|---
alloca|alloca
branch conditionally|br
branch unconditionally|bru
call|call
def|def
getelementptr|getelementptr
hello world program|hello
icmp|icmp
load|load
ret|ret
store|store

The syntax highlighting is basic, but it is enough to help clarify the elements of an LLVM file.


## Contributing to LLVM.tmbundle

I'm happy to merge any fixes/additions people might have. 

A word of caution on making changes outside the TextMate Bundle editor; you must make sure you create a new UUID for each new file you add to the bundle. TextMate uses the UUID to provide for a kind of inheritance and to support name changes. Most other editors which use the same files don't care about the UUIDs, but non unique UUIDs will break TextMate.

 Each file contains a UUID that can not be replicated in any other file in any other Bundle. The TextMate Bundle editor will take care of this for you automatically, but if you use a text editor you will need to generate a new UUID for each new item you add to the bundle i.e. a new snippet. You can create a new UUID with `uuidgen`.

