- hosts: jenkins_slave
  become: true
  tasks:
    - name: update ubuntu repo and cache
      apt:
        update_cache: yes
        cache_valid_time: 360

    - name: Install Java Version 17
      apt:
        name: openjdk-17-jdk
        state: present

    - name: Download Maven Packages
      get_url:
        url: https://archive.apache.org/dist/maven/maven-3/3.9.11/binaries/apache-maven-3.9.11-bin.tar.gz
        dest: /opt

    - name: Extract Maven Packages
      unarchive:
        src: /opt/apache-maven-3.9.11-bin.tar.gz
        dest: /opt
        remote_src: yes
