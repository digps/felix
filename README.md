# felix
Mirror of Apache Felix

#
# clone new copy of apache-felix project.
#

# git clone: copies all remote branches...
#git clone https://github.com/apache/felix.git apache-felix-main

# the long way, alternatively fetch single refs
mkdir apache-felix-main
cd apache-felix-main
git init
git fetch https://github.com/apache/felix.git trunk:refs/remotes/origin/trunk
git checkout -b upstream origin/trunk

# cleanup branch, make "main" the only content of repo
git filter-branch --subdirectory-filter main/ --

# now push it to our github repo.
git push digfelix upstream:org.apache.felix.main-upstream
