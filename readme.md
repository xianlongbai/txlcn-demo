txlcn 5.0 demo


使用说明:

1. 本Demo基于[txlcn-最新发布](https://github.com/codingapi/tx-lcn)版本
2. 启动Demo前需先启动事务管理器TM（txlcn-demo-tm）。
3. 更多信息见官网 [https://www.txlcn.org](https://www.txlcn.org)   
4. [性能测试报告](https://txlcn.org/zh-cn/docs/test.html)

启动依赖：
  tx-manager:
    mysql依赖:
      初始化表：
        CREATE TABLE `t_tx_exception`  (
        `id` BIGINT(20) NOT NULL AUTO_INCREMENT,
        `group_id` VARCHAR(64) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NULL DEFAULT NULL,
        `unit_id` VARCHAR(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NULL DEFAULT NULL,
        `mod_id` VARCHAR(128) CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci NULL DEFAULT NULL,
        `transaction_state` TINYINT(4) NULL DEFAULT NULL,
        `registrar` TINYINT(4) NULL DEFAULT NULL,
        `remark` VARCHAR(4096) NULL DEFAULT  NULL,
        `ex_state` TINYINT(4) NULL DEFAULT NULL COMMENT '0 未解决 1已解决',
        `create_time` DATETIME(0) NULL DEFAULT NULL,
        PRIMARY KEY (`id`) USING BTREE
       ) ENGINE = INNODB AUTO_INCREMENT = 1 CHARACTER SET = utf8mb4 COLLATE = utf8mb4_general_ci ROW_FORMAT = DYNAMIC;
    
    redis依赖
      配置好连接参数即可
      
  tx-client:
    注册中心依赖：consul
    windows下安装解压启动：consul agent -dev -ui
    
  
