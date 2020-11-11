# ssh to ec2 box

chmod 400 /path/my-key-pair.pem

ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name

# Prevent ssh connection from timeout

Log in as root

Edit the file at /etc/ssh/sshd_config

Add this line to the file: ClientAliveInterval 60

sudo systemctl restart sshd.service  

