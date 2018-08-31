
# SVN搭建

<hr>
<br>
<h3>Linux下SVN的搭建启动</h2>

一、安装<br>
yum -y install subversion<br>
二、创建SVN目录<br>
mkdir /usr/svn/svnrepos<br>
三、创建仓库<br>
svnadmin create /var/svn/svnrepos/eg:shop<br>
四、修改配置<br>
(配置文件已上传) <br>
五、启动<br>
svnserve -d -r /usr/svn/svnrepos





