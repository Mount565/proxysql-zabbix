# proxysql-zabbix

This repository contains scripts, config and template for Zabbix to monitor ProxySQL.
requires mysql-connector-python  
Run the python script on python2.7,install requirement:
```
sudo pip install mysql-connector-python
```

All the status variables can be monitored:
```
mysql> select * from stats_mysql_global;
+------------------------------+----------------+
| Variable_Name                | Variable_Value |
+------------------------------+----------------+
| ProxySQL_Uptime              | 180518         |
| Active_Transactions          | 37             |
| Client_Connections_aborted   | 0              |
| Client_Connections_connected | 63             |
| Client_Connections_created   | 2930           |
| Server_Connections_aborted   | 0              |
| Server_Connections_connected | 63             |
| Server_Connections_created   | 1647           |
| Server_Connections_delayed   | 0              |
| Client_Connections_non_idle  | 63             |
| Queries_backends_bytes_recv  | 37386831777    |
| Queries_backends_bytes_sent  | 35720631484    |
| Queries_frontends_bytes_recv | 36121023200    |
| Queries_frontends_bytes_sent | 214844188883   |
| Query_Processor_time_nsec    | 0              |
| Backend_query_time_nsec      | 0              |
| mysql_backend_buffers_bytes  | 19286784       |
| mysql_frontend_buffers_bytes | 4128768        |
| mysql_session_internal_bytes | 163856         |
| Com_autocommit               | 0              |
| Com_autocommit_filtered      | 0              |
| Com_commit                   | 0              |
| Com_commit_filtered          | 0              |
| Com_rollback                 | 0              |
| Com_rollback_filtered        | 0              |
| Com_backend_change_user      | 13             |
| Com_backend_init_db          | 12             |
| Com_backend_set_names        | 0              |
| Com_frontend_init_db         | 3              |
| Com_frontend_set_names       | 1461           |
| Com_frontend_use_db          | 0              |
| Com_backend_stmt_prepare     | 0              |
| Com_backend_stmt_execute     | 0              |
| Com_backend_stmt_close       | 0              |
| Com_frontend_stmt_prepare    | 0              |
| Com_frontend_stmt_execute    | 0              |
| Com_frontend_stmt_close      | 0              |
| Mirror_concurrency           | 0              |
| Mirror_queue_length          | 0              |
| Questions                    | 79304682       |
| Slow_queries                 | 2985           |
| Servers_table_version        | 1              |
| MySQL_Thread_Workers         | 8              |
| MySQL_Monitor_Workers        | 16             |
| ConnPool_get_conn_immediate  | 0              |
| ConnPool_get_conn_success    | 2928           |
| ConnPool_get_conn_failure    | 0              |
| MyHGM_myconnpoll_get         | 2928           |
| MyHGM_myconnpoll_get_ok      | 2928           |
| MyHGM_myconnpoll_push        | 3752           |
| MyHGM_myconnpoll_destroy     | 0              |
| MyHGM_myconnpoll_reset       | 3752           |
| SQLite3_memory_bytes         | 3301168        |
| ConnPool_memory_bytes        | 2192           |
| Stmt_Client_Active_Total     | 0              |
| Stmt_Client_Active_Unique    | 0              |
| Stmt_Server_Active_Total     | 0              |
| Stmt_Server_Active_Unique    | 0              |
| Stmt_Max_Stmt_id             | 1              |
| Stmt_Cached                  | 0              |
| Query_Cache_Memory_bytes     | 0              |
| Query_Cache_count_GET        | 0              |
| Query_Cache_count_GET_OK     | 0              |
| Query_Cache_count_SET        | 0              |
| Query_Cache_bytes_IN         | 0              |
| Query_Cache_bytes_OUT        | 0              |
| Query_Cache_Purged           | 0              |
| Query_Cache_Entries          | 0              |
+------------------------------+----------------+
68 rows in set (0.01 sec)

```
To add a new status monitor item, just clone an `Item` in zabbix web interface and change the variable name. No other configrations needed.

