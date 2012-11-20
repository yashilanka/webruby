# Introduction

This is a top experiment trying to bring mruby to the browser. It uses [emscripten]
(https://github.com/kripken/emscripten) to compiles the mruby source code into
JavaScript and runs in the browser.

The build script and patches I wrote are licensed under the [MIT license]
(http://www.opensource.org/licenses/mit-license.php), the entrypoint file at
`src/main.c` is taken from [An Introduction to Mini Ruby]
(http://geekmonkey.org/articles/36-an-introduction-to-mini-ruby) and
belongs to the original author, Fabian Becker.

# How to use this

    $ git clone git://github.com/xxuejie/mruby-browser.git
    $ ./scripts/bootstrap
    $ node build/mruby.js
    Ruby is awesome!
    Ruby is awesome!
    Ruby is awesome!
    Ruby is awesome!
    Ruby is awesome!

If you make changes to the source code, you can simply use `make` to rebuild it. The default target generates a js file. You can also use the `webpage` target to generate a webpage:

    $ make webpage
    $ open build/mruby.html

# Unit test status

* argumenterror.rb: ALL PASS
* array.rb: ALL PASS
* basicobject.rb: ALL PASS
* bs_block.rb: ALL PASS
* bs_literal.rb: ALL PASS
* class.rb: ALL PASS
* comparable.rb: ALL PASS
* enumerable.rb: ALL PASS
* exception.rb: Crashed when running 'Exception 14'
* false.rb: ALL PASS
* float.rb: Fail: Float#round [15.2.9.3.12]
* hash.rb: ALL PASS
* indexerror.rb: ALL PASS
* integer.rb: ALL PASS
* kernel.rb: ALL PASS
* literals.rb: ALL PASS
* localjumperror.rb: ALL PASS
* math.rb: ALL PASS(with Pull Request 724 of emscripten)
* module.rb: ALL PASS
* nameerror.rb: ALL PASS
* nil.rb: ALL PASS
* nomethoderror.rb ALL PASS
* numeric.rb ALL PASS
* object.rb: ALL PASS
* proc.rb: Crashed when running 'Proc.new', '15.2.17.3.1'
* range.rb: ALL PASS
* rangeerror.rb: ALL PASS
* regexperror.rb: ALL PASS
* runtimeerror.rb: ALL PASS
* standarderror.rb: ALL PASS
* string.rb: Fail: String#to_f [15.2.10.5.39]
* struct.rb: ALL PASS
* symbol.rb: ALL PASS
* syntax.rb: ALL PASS
* time.rb: ALL PASS
* true.rb: ALL PASS
* typeerror.rb: ALL PASS

# Notes

This is currently only an experiment! It still contains a lot of bugs and I'm now working to fix them. Feel free to write to me(xxuejie@gmail.com) if you have any comments or find any bugs. I would really appreciate it:)

