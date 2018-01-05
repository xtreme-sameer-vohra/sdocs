git clone git@github.com:pivotal-cf/greenhouse-dotfiles.git
cd greenhouse-dotfiles/
source bash_profile
mkdir -p /Users/svohra/workspace/dotfiles/lpass
fly-stemcells
fly-stemcells 2012 -dev -name sameer-proxy -b master -ci master
fly -t private get-pipeline -p windows-stemcells-2012-devsameer-proxy > /tmp/dev-sameer-proxy.yml
fly -t private set-pipeline -p windows-stemcells-2012-devsameer-proxy -c /tmp/dev-sameer-proxy.yml
