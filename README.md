# Spring Music Deployment

The default manifest is for deploying to a BOSH-Lite on Virtualbox.  
There is a bunch of BOSH operations files included to 'patch' the deployment for
deploying to other IaaS.

If you look at the `ops/` directory you should be able to determine what operations files to include if you want to deploy to other IaaS's.


## Deplying to BOSH-Lite on Virtualbox

This assumes you have followed my [workshop](https://bosh.valueline.io/bootstrap-bosh-director/workstation/intro/) on bootstrapping a BOSH director on your workstaiton.

* Deploy

``` bash
bosh -e vbox deploy -d spring-music-demo manifest.yml
```

* Check the deployment

``` bash
bosh -e vbox -d spring-music-demo vms
```

## Deploying to AWS

This assumes you have followed my [workshop](https://bosh.valueline.io/bootstrap-bosh-director/aws/intro/) on bootstrapping a BOSH director in AWS.

* Deploy

:TODO:Needs Testing

``` bash
bosh -e aws deploy                 \
  -d spring-music-demo manifest.yml \
  -o ops/aws.yml                    \
  -v vars/aws.yml
```

* Check deployment

``` bash
bosh -e aws -d spring-music-demo vms
```

