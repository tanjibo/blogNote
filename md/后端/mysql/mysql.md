### <center>mysql
---

```
DROP TABLE IF EXISTS `user`;
CREATE TABLE `user` (
  `role_id` int(11) NOT NULL COMMENT '角色id',
  `right_id` int(11) NOT NULL,
  PRIMARY KEY (`role_id`,`right_id`),
  UNIQUE KEY `right_id` (`right_id`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8;


```
