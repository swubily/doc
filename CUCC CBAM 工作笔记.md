sudo systemd-nspawn -D /mnt/sysimage/ /sbin/init

scp root@10.15.171.198:/root/packages/*.rpm .
scp root@10.15.171.198:/root/packages/*.jar .

rpm -Uvh *.rpm
cp *.jar /opt/nokia/cbam/bin/

systemctl stop mariadb
systemctl disable mariadb
chkconfig --del mysql
rm -fr /var/lib/mysql/*

vi /usr/lib/systemd/system/app-mariadb.service
[Unit]
Description=MariaDB Service Monitor
After=network.target
[Install]
WantedBy=multi-user.target

sudo sed -i "s/WantedBy=app.target/WantedBy=multi-user.target/g"  `grep WantedBy=app.target -rl /mnt/sysimage/usr/lib/systemd/system/app-mariadb.service`

sed -i \"s/After=multi-user.target/After=network.target/g\"  `grep After=multi-user.target -rl /mnt/sysimage/usr/lib/systemd/system/app-mariadb.service`

sed -i "s/oldString/newString/g"  `grep oldString -rl /path`

systemctl daemon-reload

history -c

qemu-img convert -f raw -O qcow2 -c build.image build.image.qcow2

scp build.image.qcow2 root@10.75.195.74:/root

openstack image create --file build.image.qcow2 --disk-format qcow2 --container-format bare demo-image-3-1-2

nova boot --flavor m1.small --image CBAM18-installer --key-name test --security-group default --nic net-name=v402-NODE003-CB-PROVIDER cbam-installer

heat stack-create --poll -f main_stage1.yaml -Pf helper=helper.json -Pf data=input.json.3 vnfm-verify
heat stack-update -f main_stage2.yaml -Pf helper=helper.json -Pf data=input.json.3 vnfm-verify
heat stack-create --poll -f main_stage_vip.yaml -Pf helper=helper.json -Pf data=input_vip.json vnfm-unicom-tiger

heat stack-create --poll -f main_stage_vip.yaml -Pf helper=helper.json -Pf data=input_vip.json vnfm-unicom-andy
heat stack-create --poll -f main_stage1.yaml -Pf helper=helper.json -Pf data=input.json vnfm-unicom-andy-1
heat stack-update -f main_stage2.yaml -Pf helper=helper.json -Pf data=input.json vnfm-unicom-andy-1


     heat stack-create --poll -f main_stage1.yaml -Pf helper=helper.json -Pf data=input-node1.json vnfm-zou-1
     heat stack-create --poll -f main_stage1.yaml -Pf helper=helper.json -Pf data=input-node2.json vnfm-zou-2
     heat stack-create --poll -f main_stage1.yaml -Pf helper=helper.json -Pf data=input-node3.json vnfm-zou-3
    
     heat stack-update -f main_stage2.yaml -Pf helper=helper.json -Pf data=input-node1.json vnfm-zou-1
     heat stack-update -f main_stage2.yaml -Pf helper=helper.json -Pf data=input-node2.json vnfm-zou-2
     heat stack-update -f main_stage2.yaml -Pf helper=helper.json -Pf data=input-node3.json vnfm-zou-3

mysql -u vnfm -h 10.75.153.52 -p vnfm

/opt/nokia/cbam/bin/db-creator.sh

debug:

java -jar db-creater-0.0.1-SNAPSHOT.jar --spring.datasource.url=jdbc:mariadb://10.15.171.217/vnfm --spring.datasource.username=vnfm --spring.datasource.password=vnfm@db

systemctl status cbam-operability-distribution


journalctl -xu cbam-operability-distribution>11

curl --header 'PRIVATE-TOKEN: yUu6Yf--3jmZYZJnFSzY' https://gitlabe1.ext.net.nokia.com/api/v4/projects/vnfm%2Fplatform/jobs/1132315/artifacts

curl --header 'PRIVATE-TOKEN: yUu6Yf--3jmZYZJnFSzY' https://gitlabe1.ext.net.nokia.com/api/v4/projects/vnfm%2Flcm/jobs/1132002/artifacts

