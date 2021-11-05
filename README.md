# Linux-Archiving-and-Logging-Data-Homework
Homework 5 Archiving and Logging Data
1: Command to extract the TarDocs.tar archive to the current directory:
tar -xf TarDocs.tar -C /home/sysadmin/Projects

2: Command to create the Javaless_Doc.tar archive from the TarDocs/ directory, while excluding the TarDocs/Documents/Java directory:  
tar cvvWf Javaless_Doc.tar TarDocs/ /home/sysadmin/TarDocs/Documents/Java

3: Command to ensure Java/ is not in the new Javaless_Docs.tar archive:
tar cvf Javaless_Docs.tar --exclude="Java" /home/sysadmin/Projects/TarDocs
Critical analysis question;
Why wouldn't you use the options -x and -c at the same time with tar?
Because when both are used at the same time they will not conflate into a multipurpose tool.  But rather will recursively call on one another.

1: Cron job for backing up the /var/log/auth.log file:
0 6 * * 0 ./authlog_backup_script
"authlog_backup_script" Contains:
#!/bin/bash
tar cf logs_backups.tar /var/log/auth.log
()end

2:  #!/bin/bash
free -h > ~/backups/freemem/free_mem.txt
du -h > ~/backups/diskuse/disk_use.txt
lsof > ~/backups/openlist/open_list.txtdf -h > 
~/backups/freedisk/free_disk.txt

3: Command to make the system.sh script executable:
chmod +x system.sh
Optional: ~/Scripts/system.sh && ls -R ~/backups


4: Commands to test the script and confirm its execution:
./system.sh

1: Run sudo nano /etc/logrotate.conf to edit the logrotate configuration file.
Configure a log rotation scheme that backs up authentication messages to the /var/log/auth.log.
/var/log/auth.log {
missingok
monthly
create 0660 root utmp
rotate 1
}

Bonus
1.systemctl status auditd.service
2+3
-D
-b 8192
-f 1
--backlog_wait_time 0
-w /etc/shadow -p wa -k shadow
-w /etc/passwd -p wa -k passwd
4. systemctl restart auditd.service


