FROM debian:8

MAINTAINER nikitasius "https://github.com/nikitasius"

RUN apt-get update
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN useradd evegate -d /home/evegate
RUN mkdir -p /home/evegate/.ssh
RUN touch /home/evegate/.ssh/authorized_keys
RUN chmod 700 /home/evegate/.ssh
RUN chmod 600 /home/evegate/.ssh/authorized_keys
RUN chown -R evegate:evegate /home/evegate/.ssh
RUN echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCxPlU791bokZmmtzXL3XV9Ux12KgCZVAjxogAhSDDGvi+WDhTYr+WJihrDqLStvBoKMc/rAr2md0e3+XQdt9M3WnCxikD8DFHtc2LQH6H9nFvC/qAavBEq8thKrLnZno0U9X8PsO/JHyGRMQ752Wlzv4UdZErtyHrl1LZs1YkHfwkr1XmHMapRubZ0zfhgsE8eRHuc7G6B8bwSu8MQRK0SN6lkF1GASv+SNbWRHtkyBMg8hJODk2FyOWUST2i7iF0eF5EV14RN3agZvxfzdqGxIMbtmx2oScprS3lq4EwU03SFMvnb3YCQ5RkJ2JKnm/guSEVnvb2eUWpQZfJRjWoHEijX7TPFc4uHyBBcbV2iOoZhWcFEcwe2Es5dps94LD/r6N9L7mtMw5EZIODVtGL5hv21HZQz/a1REua03RmZaCu8/VaPc68WfxT7tX9WKIZOH2o2PZqAqBBp2ygW1tAVW3RU4Ek9qrjfFG/beHbz5TfzW+n4M+VWjqIU8MrG+3qwEN3Lqi/MyrHKgbJ29aFZldMT+JEvC+RTiTGKTShgVdnIbxxtDY+TJDPdamCfgTOtocjJefnnP9pJRf1YVt6epYwUeZxKG9sbnJ8Ux1Th2YZ6P0qrmlSiFuDyqaDeb3vsiwwffoOziT23ZgRNsnZvdp9oj3HKIT3O66xHMeOC4w== shieldmaller' > /home/evegate/.ssh/authorized_keys
RUN echo 'root:root' |chpasswd
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^PubkeyAuthentication\s+.*/PubkeyAuthentication yes/' /etc/ssh/sshd_config

EXPOSE 22
CMD    ["/usr/sbin/sshd", "-D"]
