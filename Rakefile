task :default do
  exec "jekyll serve --watch"
end

def write_page(gif, page)
  require 'fileutils'

  FileUtils.cp gif, "./gifs/#{page}.gif"
  title = page < 10 ? "000#{page}" : "00#{page}" # i am too tired to remember sprintf
  File.write "_posts/2014-09-04-#{title}.md", <<EOF
---
layout: page
title: #{page}
---

<img src="{{ site.url }}/gifs/#{page}.gif" />

<a href="">&#8627;</a>

EOF
end

task :add do
  gifs = Dir["./gifs/*.gif"]
  write_page ENV["GIF"], gifs.size + 1
end
