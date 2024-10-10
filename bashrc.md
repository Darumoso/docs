# .bashrc

```

# User specific aliases and functions
shopt -s expand_aliases

modules_shell="bash"
[ -n module ] && module purge
umask 007

export USER_PREFERRED=$USER
module purge

export CPL_ZIP_ENCODING=UTF-8
#export WORK2=${WORK2%/*}/stampede3


alias source_environment='cd $RSMASINSAR_HOME; export PATH=/bin; unset PYTHONPATH; source setup/platforms_defaults.bash; source setup/environment.bash; export PATH=$ISCE_STACK/topsStack:$PATH; source ~/accounts/alias.bash; source ~/accounts/login_alias.bash; cd -;'


alias s.bw2='export RSMASINSAR_HOME=~/code/rsmas_insar; source_environment'

s.bw2

```
