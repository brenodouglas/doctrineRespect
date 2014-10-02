Doctrine configuration for Respect/Rest
===============

Integration doctrine in project Respect/Rest

Require
  PHP >= 5.3
  
In index.php

  <?php 
      require 'autoload.php';
      
      \RespectDoctrine\Doctrine\Doctrine::setConfigDir("config.php");
      $doctrine = new Doctrine();
      $em = $doctrine->getEntityManager();
      
  
In config.php
  <?php 
    return [
    'database' => [
        
        'default' => 'mysql',
        
        'mysql' => [
            'dbname' => "application",
            'user' => 'root',
            'port' => null,
            'password' => '159951',
            'host' => 'localhost',
            'driver' => 'pdo_mysql'
        ],

        'pgsql' => [
            'dbname' => "application",
            'user' => 'root',
            'port' => 5232,
            'password' => '',
            'host' => 'localhost',
            'driver' => 'pdo_pgsql'
        ]

    ],

    'doctrine' => [
        /** Namespaces on Entity mapped */
        'entity' => [
            __DIR__."/Api/Entity"
        ],
        /** Dir of metadatas generate */
        'metadata' => __DIR__."/../cache/doctrine"
    ]

];


  



