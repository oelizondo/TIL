#Thor
A few months ago I wrote a static site generator called Sofia. It's was built on bash, and would basically ```curl``` all the files necessary from different gists I'd written and then run npm install and take a long while to load the whole thing. The next problem would be the server and a build file that contained everything, and deployment was tedious. I wanted to build Sofia that would be cross-plaform (Sofia is only for *NIX machines) and also be written in ruby. Why? I like Ruby.

And so I looked for something that could help me build CLIs in Ruby. Thata's when Thor came in.