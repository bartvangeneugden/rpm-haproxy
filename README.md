[![Github All Releases](https://img.shields.io/github/downloads/DBezemer/rpm-haproxy/total.svg)](https://github.com/DBezemer/rpm-haproxy/releases)

# A Recipe for a HAProxy 1.8 stable version RPM on CentOS / RHEL / Amazon Linux

Perform the following on a build box as a regular user.

## Install Prerequisites for RPM Creation

    sudo yum groupinstall 'Development Tools'

## Checkout this repository

    git clone https://github.com/ExpediaInc/rpm-haproxy.git
    cd ./rpm-haproxy

## Build using makefile
    make
    
Resulting RPM will be in /opt/rpm-haproxy/rpmbuild/RPMS/

## Upload via S3
    sudo yum install python-pip
    sudo pip install s3cmd
    s3cmd put haproxy-1.8.8-1.amzn1.x86_64.rpm s3://tls-test-software-repo/haproxy/haproxy-1.8.8-1.amzn1.x86_64.rpm

## Credits

Based on the Red Hat 6.4 RPM spec for haproxy 1.4 combined with work done by 
- [@nmilford](https://www.github.com/nmilford)
- [@resmo](https://www.github.com/resmo) 
- [@kevholmes](https://www.github.com/kevholmes)
- Update to 1.8 contributed by [@khdevel](https://github.com/khdevel)
- Amazon Linux support contributed by [@thedoc31](https://github.com/thedoc31)

Additional logging added based on https://www.percona.com/blog/2014/10/03/haproxy-give-me-some-logs-on-centos-6-5/
