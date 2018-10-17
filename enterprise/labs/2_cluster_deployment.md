```
{
  "timestamp" : "2018-10-17T10:04:58.270Z",
  "clusters" : [ {
    "name" : "Isalah89",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-0b035bd609900978b4f8d92bae41b6de",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8jzg9nzwotsx3n9duy11s7z1d"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-1a1effa556c5bc01b3c94c00e579ff5c",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "98389311-3481-4088-9735-88d18d96367f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3n877q831bolqiik35yilig0b"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4w3w78cnuf871m0lred1kwsow"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "n1.sebcdomain"
          }, {
            "name" : "oozie_database_password",
            "value" : "password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozieuser"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-f1c28f60e3591fc6855d2aa2f6571bda",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6qq1zrilykllpsb1j844l25r6"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "n1.sebcdomain"
        }, {
          "name" : "database_password",
          "value" : "password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "database_user",
          "value" : "hueuser"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-f1c28f60e3591fc6855d2aa2f6571bda"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-f1c28f60e3591fc6855d2aa2f6571bda",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "8d596b25-0e1e-41c5-b01f-8fd46e59840b"
          }, {
            "name" : "role_jceks_password",
            "value" : "4mq6kjlyzbnc81v3q81b6nlsq"
          }, {
            "name" : "secret_key",
            "value" : "SCFMVCHiOGksLu63SgnuDfZ0obSJcA"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1254096896"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1254096896"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "vSwQAPQKjwKWPfD0d2gNOb7mpLsW9v"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "A7xBDfFhZxoPy70qILdGz3C92gFYMk"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "Hnt8oAGU0Pw1N74JW5y4nfs3BrFr8K"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-0b035bd609900978b4f8d92bae41b6de",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-0b035bd609900978b4f8d92bae41b6de",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1clbyxnl18o5i3r8j9ta82mmu"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-16a15a57cf22584a9a265f020c340bd2",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c8dec639-bef1-4936-8262-0434f91e8739"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bwbtgnd6gauzk0e42m90yru3p"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-1a1effa556c5bc01b3c94c00e579ff5c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "98389311-3481-4088-9735-88d18d96367f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8jz5e879xrs0ksv4zslgkwbmp"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9nmgla7gpaqnkwgsj5okcusic"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-0b035bd609900978b4f8d92bae41b6de",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4mt9j7h2p0b9uezvn3n5zsvss"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5bgvvjpzk7i1k04bha2wzj37y"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-f1c28f60e3591fc6855d2aa2f6571bda",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5qhyo85pgxdqoa2kki2fz84hm"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-16a15a57cf22584a9a265f020c340bd2",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c8dec639-bef1-4936-8262-0434f91e8739"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c7n52dwre9kf4z97hepkqmmdk"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-1a1effa556c5bc01b3c94c00e579ff5c",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "98389311-3481-4088-9735-88d18d96367f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "btek35q9k43t7fqy68an0l80x"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-f1c28f60e3591fc6855d2aa2f6571bda",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8pvi90f17v8rd6l9g7s4ltgiq"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-0b035bd609900978b4f8d92bae41b6de",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "sebc"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "sebc"
          }, {
            "name" : "namenode_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "6ny4ylgmen01sd3kvexunnisu"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "sebc"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "sebc"
          }, {
            "name" : "namenode_id",
            "value" : "42"
          }, {
            "name" : "role_jceks_password",
            "value" : "dofhwjsamsmdeg8x4ca2a1oqq"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "6144"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4346"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "XBC0FN53QkqCInAaYd93Vy3wBJ25ls"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-0b035bd609900978b4f8d92bae41b6de",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "31wch978v52virwwp8eqngq9s"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-0b035bd609900978b4f8d92bae41b6de",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d4x9laem5nwkccmpky6cbkfd"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-16a15a57cf22584a9a265f020c340bd2",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c8dec639-bef1-4936-8262-0434f91e8739"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "rwz5yoxwuu7vngybjstee3um"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1a1effa556c5bc01b3c94c00e579ff5c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "98389311-3481-4088-9735-88d18d96367f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "951lb0uriri2b85xecxgqhnvv"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ceqbfiq9awj9unsi47l9wlz8n"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-1a1effa556c5bc01b3c94c00e579ff5c",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "98389311-3481-4088-9735-88d18d96367f"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "49"
          }, {
            "name" : "role_jceks_password",
            "value" : "86niqrfixpiap6rk9ztws34w6"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1254096896"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "125409689"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "1254096896"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1385955328"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "233"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "n1.sebcdomain"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "password"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "hiveuser"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-f1c28f60e3591fc6855d2aa2f6571bda",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "beptrz5bhujh0dadjl2s0788l"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-20d66e93d67dd5ec2708832504f20f6e",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4hxf4k4kx53uyv2ohrf0l73av"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d",
    "ipAddress" : "172.31.33.12",
    "hostname" : "n1.sebcdomain",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "730168e7-d288-4849-87a9-c1b9089a71e4",
    "ipAddress" : "172.31.33.154",
    "hostname" : "n2.sebcdomain",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "b38bbd62-82c0-4da9-8cee-c7d089f6db9a",
    "ipAddress" : "172.31.36.203",
    "hostname" : "n3.sebcdomain",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "98389311-3481-4088-9735-88d18d96367f",
    "ipAddress" : "172.31.45.194",
    "hostname" : "n4.sebcdomain",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c8dec639-bef1-4936-8262-0434f91e8739",
    "ipAddress" : "172.31.40.140",
    "hostname" : "n5.sebcdomain",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__96428ad6-3aef-4498-81e8-e7bdbe19b11a",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4af46864d6fa4bd33be9c618b4447e407e6f5ad957106c9a9e3665fba8d1b8da",
    "pwSalt" : 3812859396982895317,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-f1c28f60e3591fc6855d2aa2f6571bda",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "ffd1542f96f9a0e20e70ee44336f92711e82ab9f4397eb7b12456d5bc30b5f6a",
    "pwSalt" : 252169266485327703,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-f1c28f60e3591fc6855d2aa2f6571bda",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16881a78d93aa9d54e2f617c36d657ade6db636ef077e97e35f4ab407cb7ef8f",
    "pwSalt" : -1736959018048070487,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-f1c28f60e3591fc6855d2aa2f6571bda",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "514e64f646612b83a376733d9cf120d5b5c3dc5f01996bc0f6882eefa43ebbd9",
    "pwSalt" : 3417144848418388270,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-f1c28f60e3591fc6855d2aa2f6571bda",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "bad96bc446dec394226101c17afb3e76a5654cec164236e57b1ffd7ab2b4b659",
    "pwSalt" : -5591928538603892393,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-f1c28f60e3591fc6855d2aa2f6571bda",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3523ee782fc0de3eea55cdc6b6557f8bcd6e06cf1780ecfb8b233dac851ec780",
    "pwSalt" : 4575724273029531125,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "0f46bf9f9935a29f5f5b602b0860bc70cd36d92b7d59ce5b1413d086c747eb94",
    "pwSalt" : -7907054453675963271,
    "pwLogin" : true
  }, {
    "name" : "isalah89",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "d0a153e91089e8d457d97e7a73a556c22ab9f6368011f612991d780af5d5c6a0",
    "pwSalt" : -2037731799830194451,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "c2278674b421a67119517afd29836bc1d2bf255354238e47d3d9f9f914391c2e",
    "pwSalt" : -5993918849366839183,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20180328-1830",
    "gitHash" : "f90c58536c252d70a23bde6d94514d92a1f111d4",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "n1.sebcdomain"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rmanuser"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-f1c28f60e3591fc6855d2aa2f6571bda",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "f2vnxxiou4rjqbz902adow0st"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-f1c28f60e3591fc6855d2aa2f6571bda",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "el0pvswe7svmljbjkfxl8foo6"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-f1c28f60e3591fc6855d2aa2f6571bda",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5n9m4llhwcygzcjoutwsotniu"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-f1c28f60e3591fc6855d2aa2f6571bda",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5tn6pmg2qs2jx9skn0hpcb1mv"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-f1c28f60e3591fc6855d2aa2f6571bda",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "60223daf-b6a5-4640-a0d6-0ac04cfe1c1d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "a5wgylgjfn92xg9dosymy45al"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 15:50"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```