rAthenaCN ������Ŀ��
=======

����״̬: [![Build Status](https://travis-ci.org/rathena/rathena.png?branch=master)](http://www.rAthenaCN.com)

Ŀ¼
---------
1. ��Ŀ�ռ�
2. ��ȡ׼��
3. ��װָ��
4. �������
5. ��������
6. �����ĵ�

1. ��Ŀ�ռ�
---------
rAthena��һ��Э�����������Ŀ��Χ�ƴ���ǿ��Ĵ��Ͷ������߽�ɫ������Ϸ��MMORPG�������������С�
��C��д���ó���ǳ��������ṩNPC�޸ġ�����Ŀ��������ص�һ��־Ը�߹�ͬ����
�Լ��ṩ������֤��֧�ֵľ޴�������rAthena��eAthena��Ŀ��������

2. ��ȡ׼��
---------
�ڰ�װrAthena֮ǰ��������ҪĳЩ���ߺ�Ӧ�ó������ڿ��õĲ�ͬ����ϵͳ֮��������ͬ���������潫�ֽ�ΪWindows��Linux���Ⱦ�������

* Windows
	* MySQL ( http://www.mysql.com/downloads/mysql/ )
	* MySQL Workbench ( http://www.mysql.com/downloads/workbench/ )
	* MS Visual C++ ( http://www.microsoft.com/visualstudio/en-us/products/2010-editions/visual-cpp-express )
	* TortoiseGIT ( http://code.google.com/p/tortoisegit/ )
	* MSysGit ( http://msysgit.github.io/ or https://github.com/msysgit/git/releases )

* Linux (����������ƿ�����ҪĳЩ�ַ��汾���ض��汾��)
	* gcc
	* make
	* mysql
	* mysql-devel
	* mysql-server
	* pcre-devel
	* zlib-devel
	* git

3. ��װָ�� 
---------
������һ��ǳ���̵İ�װ˵�����й����Ĳ���ϵͳ�ĸ�����ָ�ϣ������Wiki (��ĩβ������)

* Windows
	* Install prerequisites
	* Create a folder to download rAthena into (e.g. C:\rAthena)
	* Right click this folder and select "Git Clone"
	* Paste the GitHub URL into the box:

				https://github.com/rathena/rathena.git
	* Open MySQL Workbench and create an instance to connect to your MySQL Server
	* Create a database (rathena), a user (rathena), give permissions (GRANT SELECT,INSERT,UPDATE,DELETE)
		and then login using the new user
	* Use MySQL Workbench to run the .sql files in /sql-files/ on the new rathena database

* Linux
	* Type:
		* (For CentOS)

				yum install gcc make mysql mysql-devel mysql-server pcre-devel zlib-devel git
		* (For Debian)

				apt-get install git make gcc libmysqlclient-dev zlib1g-dev libpcre3-dev
	* Type:

				mysql_secure_installation
	* Start your MySQL server
	* Setup a MySQL user:

				CREATE USER 'rathena'@'localhost' IDENTIFIED BY 'password';
	* Assign permissions:

				GRANT SELECT,INSERT,UPDATE,DELETE ON `rathena\_rag`.* TO 'rathena'@'localhost';
	* Clone a GIT repository:

				git clone https://github.com/rathena/rathena.git ~/rathena
	* Insert SQL files:

				mysql --user=root -p rathena_rag < trunk/sql-files/main.sql (and others)
	* Configure and compile:

				./configure && make clean && make server
	* When you're ready, start the servers:

				./athena-start start



4. �������
---------
�����������������ʱ�������⣬��Ӧ�����ĵ�һ�����Ǽ�����̨�Ϸ�����ʲô��
��������������ǣ�����֧�����ⶼ����ͨ���鿴�����Ĵ�����Ϣ�������

����:

* ���ĵ�ͼ�������ϳ������´���:

			[Error]: npc_parsesrcfile: Unable to parse, probably a missing or extra TAB in 
				file 'npc/custom/jobmaster.txt', line '17'. Skipping line...
				* w1=prontera,153,193,6 script
				* w2=Job Master
				* w3=123,{
				* w4=

    ����㿴������������������������ (������һ�������) TAB.
		ͨ���鿴�ⲿ�ִ�����Ժ����׵ؽ���������:

				* w1=prontera,153,193,6 script

	If there was a TAB where it's supposed to be, that line would have prontera,153,193,6 at w1
		and 'script' at w2. As there's a space instead of a TAB, the two sections are read as a
		single parameter.

* You have a default user/password warning similar to the following:

			[Warning]: Using the default user/password s1/p1 is NOT RECOMMENDED.
			[Notice]: Please edit your 'login' table to create a proper inter-server user/pa
			ssword (gender 'S')
			[Notice]: and then edit your user/password in conf/map_athena.conf (or conf/impo
			rt/map_conf.txt)

    Relax. This is just indicating that you're using the default username and password. To
		fix this, check over the part in the installation instructions relevant to the `login` table.
	
* Your map-server outputs the following:

			[Error]: make_connection: connect failed (socket #2, error 10061: No connection
			could be made because the target machine actively refused it.
			)!

    If this shows up on the map server, it generally means that there is no Char Server available
		to accept the connection.



5. ��������
---------
* rAthenaCN ��ҳ [����]
	* http://www.rAthenaCN.com/
	
* rAthenaCN ģ����Դ�� [����] GIT �����
	* https://github.com/rAthenaCN/rAthenaCN.git

* ROClientFullCN �����ͻ��� [����] GIT �����
	* https://github.com/rAthenaCN/ROClientFullCN.git

* ROClientPatchCN �ͻ��˲��� [����] GIT �����
	* https://github.com/rAthenaCN/ROClientPatchCN.git

* rAthena ��̳ [�ٷ�]
	* https://rathena.org/
	
* rAthena ģ����Դ�� [Ӣ��] GIT �����
	* https://github.com/rathena/rathena
	
* ����ϵͳ��װ˵��
	* Windows: https://rathena.org/wiki/Installation_on_Windows
	* CentOS: https://rathena.org/wiki/Installation_(CentOS)
	* Debian: https://rathena.org/wiki/Installation_(Debian)
	* FreeBSD: https://rathena.org/wiki/Installation_(FreeBSD)
	
* rAthena [�ٷ�] IRC Channel
	* irc://irc.rizon.net/rathena
	* Web Chat: https://rathena.org/board/page/chat.html

* rAthena [�ٷ�] Wiki
	https://rathena.org/board/index.php?app=ipbwiki

* Fork and Pull Request Q&A
	https://rathena.org/board/topic/86913-pull-request-qa/


6. �����ĵ�
---------
rAthenaӵ�д����İ����ļ���λ��/ doc /Ŀ¼�е�ʾ��NPC�ű�����Щ������NPC�ű����atcommands��@����
��Ȩ�ޣ���Ŀ��������ݰ��ṹ�Լ���������������ϸ���͡����ǽ��������û���ʱ���������ط�Ѱ�����֮ǰ�鿴��Ŀ¼��
