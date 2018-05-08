# 数据库 - mysql
## 什么是 mysql
* mysql 是一个关系型的数据库,现在是 oracle 公司的一款软件
* 这是一款使用费用广泛的软件,很多 java,php 语言的开发,数据库语言都选的 mysql( 开源免费)
* 它分为企业版和社会版,我们选择社会版 community

## mysql 的安装

## mac 运行 mysql
想要启动 mysql,我在安装完 mysql 之后执行
`mysqld start`
结果报错了

```
mysqld: Can't change dir to '/usr/local/mysql-5.7.22-macos10.13-x86_64/data/' (Errcode: 13 - Permission denied)
2018-05-08T01:55:59.265832Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
2018-05-08T01:55:59.267290Z 0 [Note] --secure-file-priv is set to NULL. Operations related to importing and exporting data are disabled
2018-05-08T01:55:59.268500Z 0 [Note] mysqld (mysqld 5.7.22) starting as process 53823 ...
2018-05-08T01:55:59.283628Z 0 [Warning] Can't create test file /usr/local/mysql-5.7.22-macos10.13-x86_64/data/wuxiaolandeMacBook-Pro.lower-test
2018-05-08T01:55:59.283686Z 0 [Warning] Can't create test file /usr/local/mysql-5.7.22-macos10.13-x86_64/data/wuxiaolandeMacBook-Pro.lower-test
2018-05-08T01:55:59.284156Z 0 [ERROR] failed to set datadir to /usr/local/mysql-5.7.22-macos10.13-x86_64/data/
2018-05-08T01:55:59.284180Z 0 [ERROR] Aborting

2018-05-08T01:55:59.284607Z 0 [Note] Binlog end
2018-05-08T01:55:59.286964Z 0 [Note] mysqld: Shutdown complete
```
这里的关键词是` permission denied`
我问了朋友安刚,他说让我把命令改成` sudo mysqld start`,
我执行这个命令,
然后遇到了第二个报错

```
2018-05-08T02:00:43.749692Z 0 [Warning] TIMESTAMP with implicit DEFAULT value is deprecated. Please use --explicit_defaults_for_timestamp server option (see documentation for more details).
2018-05-08T02:00:43.750435Z 0 [Note] --secure-file-priv is set to NULL. Operations related to importing and exporting data are disabled
2018-05-08T02:00:43.751253Z 0 [Note] mysqld (mysqld 5.7.22) starting as process 53972 ...
2018-05-08T02:00:43.761169Z 0 [Warning] Setting lower_case_table_names=2 because file system for /usr/local/mysql-5.7.22-macos10.13-x86_64/data/ is case insensitive
2018-05-08T02:00:43.761244Z 0 [ERROR] Fatal error: Please read "Security" section of the manual to find out how to run mysqld as root!

2018-05-08T02:00:43.761267Z 0 [ERROR] Aborting

2018-05-08T02:00:43.761314Z 0 [Note] Binlog end
2018-05-08T02:00:43.765076Z 0 [Note] mysqld: Shutdown complete
```
我查了下,第二个报错(关键词**Security**)是因为
> 这是因为在测试的时候，使用root来启动的。而从安全角度来讲，不建议用root用户启动。

我按照安刚给我的建议,修改下目录权限
执行
```
sudo chown -R wxl /usr/local/mysql-5.7.22-macos10.13-x86_64/data/
```


