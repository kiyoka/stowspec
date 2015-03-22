# -*- mode: ruby; -*-
#                                                  Rakefile for Stowm
# Release Engineering
#   1. rake
#      to test
#   2. rake build
#      to generate stowm-x.x.x.gem
#   3. install stowm-x.x.x.gem to clean environment and test
#   4. rake release
#   5. gem push pkg/stowm-x.x.x.gem

require 'rake'
require 'bundler/gem_tasks'
require 'jeweler2'

task :default => [:test] do
end

task :test do
  sh "/bin/rm -f test.record"
  sh "echo "" > test.log"
  sh "nendo -I ./lib  ./test/util-test.nnd                  >> test.log"
  sh "nendo -I ./lib  ./test/parseutil-test.nnd             >> test.log"
  sh "nendo -I ./lib  ./test/env-test.nnd                   >> test.log"
  sh "nendo -I ./lib  ./test/listutil-test.nnd              >> test.log"
  sh "nendo -I ./lib  ./test/specfile-test.nnd              >> test.log"
  sh "cat test.log"
  sh "cat test.record"
  sh "grep ' 0 failed, ' test.record  > /dev/null"
end

task :help do
  sh "./bin/stowm"
end

task :env do
  sh "./bin/stowm env"
end

task :cleanlist do
  sh "rm -f ~/.stowm.db"
  sh "./bin/stowm list"
end

task :list do
  sh "./bin/stowm list git"
end

task :url do
  sh "./bin/stowm https://www.kernel.org/pub/software/scm/git/git-2.3.3.tar.gz"
end

task :e do
  sh "./bin/stowm e 15"
end

task :d do
  sh "./bin/stowm d 15"
end

task :r do
  sh "./bin/stowm r 15"
end
