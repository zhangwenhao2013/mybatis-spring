MyBatis Spring Adapter
======================

[![Build Status](https://travis-ci.org/mybatis/spring.svg?branch=master)](https://travis-ci.org/mybatis/spring)
[![Coverage Status](https://coveralls.io/repos/mybatis/spring/badge.svg?branch=master&service=github)](https://coveralls.io/github/mybatis/spring?branch=master)
[![Maven central](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-spring/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis-spring)
[![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.mybatis/mybatis-spring.svg)](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/mybatis-spring/)
[![License](http://img.shields.io/:license-apache-brightgreen.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)

![mybatis-spring](http://mybatis.github.io/images/mybatis-logo.png)

MyBatis-Spring adapter is an easy-to-use Spring bridge for MyBatis sql mapping framework.

Supported Versions
------------------

- 1.3.x - Continued support for Java 6 and 7
- master (2.0.x) - Support for Java 8, Spring 5, and Junit 5 plus other java 8 requirements

Essentials
----------

* [See the published docs](http://mybatis.github.io/spring/)
* [See the snapshot docs](src/site/markdown) (Note: may contain explanation of unreleased features)


怎么使用
------


```

1: 配置
@Configuration

@Bean
 @Bean(name = "basicSqlSessionFactory")
    public SqlSessionFactoryBean MySqlSessionFactoryBean(
            @Qualifier("basicDataSource") DataSource dataSource) {
        SqlSessionFactoryBean factoryBean = new SqlSessionFactoryBean();
        // 如果这里设置了Mapper文件的路径 就可以不使用 @MapperScan @MapperScans
        return factoryBean;
    }

@Bean(name = "basicDataSource")
    public DataSource basicDataSource() {
        //return DruidDataSourceFactory.createDataSource(dsMap);
        DataSource datasource = new DataSource();
        return datasource;
    }

2:配置@Configuration  @MapperScan/@MapperScans,配置Mapper文件包路径

@MapperScan/@MapperScans的作用是将路径下的Mapper文件添加到Spring 容器,以及SqlSessionFactory.


```


@MapperScan/@MapperScans 扫描原理
------------------------------

@Import(MapperScannerRegistrar.class)

MapperScannerRegistrar 实现了 ImportBeanDefinitionRegistrar 接口


核心流程
------------------------------










