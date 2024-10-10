# platforms\_default.bash

```
###############################################
echo "sourcing ~/accounts/platforms_defaults.bash ..."
[ -z ${USER_PREFERRED} ] && export USER_PREFERRED=$USER
[ -z $HOSTNAME ] && export HOSTNAME=`hostname`
export JOBSCHEDULER=NONE
export QUEUENAME=NONE
export WORKDIR=/scratch/insarlab
export SCRATCHDIR=/scratch
export SAMPLESDIR=/home/${USER}/code/rsmas_insar/samples
export REMOTE_SERVER=centos@129.114.104.223

#############################################
########### known platforms ##################
#############################################
export NUMBER_OF_CORES_PER_NODE=16
export NUMBER_OF_THREADS_PER_CORE=1
export MAX_MEMORY_PER_NODE=16000

export JOB_SUBMISSION_SCHEME=singleTask
export JOB_SUBMISSION_SCHEME=multiTask_multiNode
export JOB_SUBMISSION_SCHEME=multiTask_singleNode
export JOB_SUBMISSION_SCHEME=launcher_multiTask_multiNode
export JOB_SUBMISSION_SCHEME=launcher_multiTask_singleNode

###############################################
if [[ ${HOSTNAME} == *stampede* ]] || [[ ${TACC_SYSTEM} == *stampede* ]]
then
  export PLATFORM_NAME=stampede2
  export JOBSCHEDULER=SLURM
  export JOBSHEDULER_PROJECTNAME=TG-EAR200012
  export WORKDIR=/work2/05861/tg851601/stampede2/insarlab
  export SCRATCHDIR=${SCRATCH}
  export QUEUE_NORMAL=skx-normal
  export QUEUE_DEV=skx-dev
  export QUEUE_DEV2=development
  export QUEUENAME=$QUEUE_NORMAL
fi
###############################################
if [[ ${HOSTNAME} == *frontera* ]] || [[ ${TACC_SYSTEM} == *frontera* ]]
then
  export PLATFORM_NAME=frontera
  export JOBSCHEDULER=SLURM
  export JOBSHEDULER_PROJECTNAME=EAR20011
  export WORKDIR=/work2/05861/tg851601/stampede2/insarlab
  export SCRATCHDIR=${SCRATCH}
  export QUEUE_NORMAL=flex
  export QUEUE_DEV=development
  export QUEUE_DEV2=development
  export QUEUENAME=$QUEUE_NORMAL
fi
###############################################
```
