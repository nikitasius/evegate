FROM debian:8

MAINTAINER nikitasius "https://github.com/nikitasius"

RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y openssh-server vim mc
RUN mkdir /var/run/sshd

RUN mkdir -p /home/evegate
RUN fallocate -l 100M /home/evegate.img
RUN mkfs /home/evegate.img
RUN mount -o loop /home/evegate.img /home/evegate

RUN useradd evegate -d /home/evegate
RUN mkdir -p /home/evegate/.ssh
RUN mkdir -p /root/.ssh
RUN touch /home/evegate/.ssh/authorized_keys
RUN touch /root/.ssh/authorized_keys

RUN chmod 700 /home/evegate/.ssh
RUN chmod 700 /root/.ssh
RUN chmod 600 /home/evegate/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/authorized_keys
RUN chown -R evegate:evegate /home/evegate/.ssh

RUN echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAEAQC+9UKK+NYcz82xBMhy4GP3TnPw2TC+B1ylMF2rTLPZqzeaoTTCqno9ubhRL8szjHHptSXtj+iVoNpHs5iYNdUGI21O84nrlflH33NISxWupPmZyolgbEoczBj/5SMzqvOtEa2nnb5Op0VVWt8yZ7R6PMuu1tRqPGU18Cuil64mK47oP4PqcalOC+9uPeBQv65hiSjAs25qkAf4cycqfLpE16rW3gZNhTQsLjDDLvfmzjnXy7XR99RrCw62vtgyc1J1/9qOpBaLgeHmILMt34lMZknFqC+2r7r+67s2zg2WXREkabibPEsJn3Dy5UTf0U6PpZ/hFAckMU1EQ6lKcUXxAbCodd/VCVVok9DZFmlC2xRh5q53D9tMB4j5iUp/TaOzrJISfuYK9gVGdPhaGH+GqfjWLTaGV68zoQnFa/V47a/MqNrWhKZfzmVNZQXexKHrlFZrBS+8tCV2Q3y6i2lMWJl/A1i6VFhZnn3GogzuvyF9jG7r+cTLHm1qOKplbvJbtXK1BgPy3tEx9DdcXd0VZKRZox3P5+eLvxHBYIzh0xYjkjCpDr4GlisKtFiZZIzAz0RijKCROikryHF7BTyfVKq5rSd9WPAcG484T+lsvg3yReQTTdTfBe+AY9gYR2BCcXOMnucsT1I9Sa0oTUnBS4PY2oQ0gzeG8im2vayiBX9ZkLbkxoqo8sN6D9beudPCZpp/2tQlw1wn+bPrrmOq1jW9PfNmKESvFFqEvwl25PTkCm2mjk/cD9NRgGGR0jT7+3pfSqGiOZzXAe1wGZCIeNRsqI2b/cEaSs1VpW4GYw0oT2/pcokj003LQjZZ9evAQHIM37+4p1U2gO/fjrNmKBiGNpT3veLzL9/A04HErv2A7RLe7qDbXnpSP/19j7dnwRRNZ9Q7UE8VgBH8zF/IQZYJt41r2ac+NL2mSc/+ii7RAlacgb/Y9GWAGifvYP2S1iQlO+JpDgaSyiAZm4uAan6hCrgG5FEBdIrFiyKU7wP3wwA5MHVJ+WlFbuyP4prcjwjWwL0adfXBuKRCVTHeDKsV/7Ucq1qj9Srl802ei1HZPNO1TUttQgf13HA0u7bbg4EH83HNobpXW80YDDVPqv4xaxglhT2VRfj3MJtCiNwATOxjY3gl42DFQanmTqFgL/5sGEcMxp71cxqJ19AtEpbPo7o3fk7ZJuRiSBGeNF4JJwqD5Wh3vje9hLceAAaNsADmgbND8InryUJPOhwQcNJmM+d6s5r7vrpRxcQrsWNiRFs9DYbcxVXYMwLR8QvwIe9Ei/59CvBReztoD2TFd/k5iyHdZY3DvPm5B1ckl7XPvH004j5yXT4ayR7O6WqfcdnuJsIhZZmTsepEb6Xh nikitas@publickeyblablabla' > /root/.ssh/authorized_keys
RUN echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQCxPlU791bokZmmtzXL3XV9Ux12KgCZVAjxogAhSDDGvi+WDhTYr+WJihrDqLStvBoKMc/rAr2md0e3+XQdt9M3WnCxikD8DFHtc2LQH6H9nFvC/qAavBEq8thKrLnZno0U9X8PsO/JHyGRMQ752Wlzv4UdZErtyHrl1LZs1YkHfwkr1XmHMapRubZ0zfhgsE8eRHuc7G6B8bwSu8MQRK0SN6lkF1GASv+SNbWRHtkyBMg8hJODk2FyOWUST2i7iF0eF5EV14RN3agZvxfzdqGxIMbtmx2oScprS3lq4EwU03SFMvnb3YCQ5RkJ2JKnm/guSEVnvb2eUWpQZfJRjWoHEijX7TPFc4uHyBBcbV2iOoZhWcFEcwe2Es5dps94LD/r6N9L7mtMw5EZIODVtGL5hv21HZQz/a1REua03RmZaCu8/VaPc68WfxT7tX9WKIZOH2o2PZqAqBBp2ygW1tAVW3RU4Ek9qrjfFG/beHbz5TfzW+n4M+VWjqIU8MrG+3qwEN3Lqi/MyrHKgbJ29aFZldMT+JEvC+RTiTGKTShgVdnIbxxtDY+TJDPdamCfgTOtocjJefnnP9pJRf1YVt6epYwUeZxKG9sbnJ8Ux1Th2YZ6P0qrmlSiFuDyqaDeb3vsiwwffoOziT23ZgRNsnZvdp9oj3HKIT3O66xHMeOC4w== shieldmaller' > /home/evegate/.ssh/authorized_keys

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^PubkeyAuthentication\s+.*/PubkeyAuthentication yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^RSAAuthentication\s+.*/RSAAuthentication yes/' /etc/ssh/sshd_config

EXPOSE 22
CMD    ["/usr/sbin/sshd", "-D"]