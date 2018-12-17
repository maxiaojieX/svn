
# SVN搭建

<hr>
<br>
<h3>CentOS下SVN的搭建启动</h2>

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

<h3>UBuntu下SVN的搭建启动</h2>
安装>apt-get install subversion<br>
创建svn目录及仓库>sudo mkdir /home/svn       sudo mkdir /home/svn/rep<br>
初始化仓库>sudo svnadmin create /home/svn/rep<br>
配置svn<br>
在conf下的svnserve.conf、passwd、authz这三个文件是用来配置svn的<br>

主要包括用户名，密码，权限等<br>

配置用户名密码<br>
vi passwd

在passwd中[users]下面，根据注释的样子配置，等于号前面的是用户名后面的是密码，用户名前不要空格，等于号两遍有空格<br>
maxiaojie = ma000000

配置分组权限<br>
vi authz<br>
在authz中[groups]下面，配置一个分组，这里配置的开发组，里面有两个用户，[/]表示所有的目录，@后面跟的是组名，这里是@develop 等于号右边的 rw表示读写权限都有<br>
[groups]
develop = maxiaojie
[/]
@develop = rw


<br>
svn全局配置，启用用户名密码，分组等<br>
配置svnserve.conf<br>
vi svnserve.conf<br>

anon-access = none<br>
auth-access = write<br>
password-db = passwd<br>
authz-db = authz<br>

启动svn服务>svnserve -d -r /home/svn/rep





