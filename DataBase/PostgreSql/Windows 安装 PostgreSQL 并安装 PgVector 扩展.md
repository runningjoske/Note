# Windows 安装 PostgreSQL 并安装 PgVector 扩展

1. 从PostgreSQL官网下载安装包，运行安装包根据步骤完成安装。
2. 打开CMD终端，执行以下命令。

```
# 初始化数据库 
# U 账号 W 命令结束后弹出密码输入  E 指定字符规则
C:\Program Files\PostgreSQL\17\bin>initdb.exe -D ..\data -U postgres -W -E UTF8

# 启动数据库 
# D 数据库地址  l 日志地址
C:\Program Files\PostgreSQL\17\bin> pg_ctl -D ..\data -l D:\logs\sqllog.txt start
```

3. 安装 Visual Studio Build Tools，勾选“使用C++的桌面开发”，右侧一定勾选"Windows 11 SDK（10.0.22621.0）"。

4. 安装扩展，执行以下命令。

   若nmake命令有问题，需要配置环境变量到Path

   D:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.42.34433\bin\Hostx64\x64

   ```
   # 设置临时系统配置
   set "PGROOT=C:\Program Files\PostgreSQL\17"
   cd %TEMP%
   git clone --branch v0.8.0 https://github.com/pgvector/pgvector.git
   cd pgvector
   nmake /F Makefile.win
   nmake /F Makefile.win install
   ```

   5. 启用PGVector

      ```
      # 访问数据库
      C:\Program Files\PostgreSQL\17\bin>psql.exe -U postgres
      # 启用插件
      postgres=# create extension if not exists vector;
      # 查看可以使用的插件
      postgres=# select * from pg_available_extensions;
      # 查看已经安装的插件
      postgres=# select * from pg_extension;
      以下是插件安装成功后的结果
        oid  | extname | extowner | extnamespace | extrelocatable | extversion | extconfig | extcondition
      -------+---------+----------+--------------+----------------+------------+-----------+--------------
       15000 | plpgsql |       10 |           11 | f              | 1.0        |           |
       16386 | vector  |       10 |         2200 | t              | 0.8.0      |           |
      ```

      