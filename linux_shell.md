# Shell命令帮助

## uniq
```text
-c, --count
	 prefix lines by the number of occurrences
	  在每列旁边显示该行重复出现的次数。
-d, --repeated
	  only print duplicate lines, one for each group
    仅显示重复出现的行列。
-D, --all-repeated[=METHOD]
	  print all duplicate lines groups can be delimited with an empty line METHOD={none(default),prepend,separate}
    全部重复的行展示，有多少重复的都展示
-f, --skip-fields=N
	  avoid comparing the first N fields
    忽略的段数，-f 1 忽略第一段
--group[=METHOD]
	  show all items, separating groups with an empty line METHOD={separate(default),prepend,append,both}

-i, --ignore-case
	  ignore differences in case when comparing
    不区分大小写
-s, --skip-chars=N
	  avoid comparing the first N characters
    根-f有点像，不过-s是忽略，后面多少个字符 -s 5就忽略后面5个字符
-u, --unique
	  only print unique lines
    去除重复的后，全部显示出来，根mysql的distinct功能上有点像
-z, --zero-terminated
	  end lines with 0 byte, not newline

-w, --check-chars=N
	  compare no more than N characters in lines
    对每行第N 个字符以后的内容不作对照
```


