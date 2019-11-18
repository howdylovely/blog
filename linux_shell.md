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

# grep
```text
grep命令的常用格式为：grep  [选项]  "模式"  [文件]
Regexp selection and interpretation:
  -E, --extended-regexp     PATTERN is an extended regular expression (ERE)
  			    开启扩展（Extend）的正则表达式。
  -F, --fixed-strings       PATTERN is a set of newline-separated fixed strings
  -G, --basic-regexp        PATTERN is a basic regular expression (BRE)
  -P, --perl-regexp         PATTERN is a Perl regular expression
  -e, --regexp=PATTERN      use PATTERN for matching
  -f, --file=FILE           obtain PATTERN from FILE
  -i, --ignore-case         ignore case distinctions
  			    忽略大小写（ignore case）。
  -w, --word-regexp         force PATTERN to match only whole words
  			   被匹配的文本只能是单词，而不能是单词中的某一部分，如文本中有liker，而我搜寻的只是like，就可以使用-w选项来避免匹配liker
  -x, --line-regexp         force PATTERN to match only whole lines
  -z, --null-data           a data line ends in 0 byte, not newline

Miscellaneous:
  -s, --no-messages         suppress error messages
  -v, --invert-match        select non-matching lines
  			    反过来（invert），只打印没有匹配的，而匹配的反而不打印。
  -V, --version             display version information and exit
      --help                display this help text and exit

Output control:
  -m, --max-count=NUM       stop after NUM matches
  -b, --byte-offset         print the byte offset with output lines
  -n, --line-number         print line number with output lines
      --line-buffered       flush output on every line
      			    显示行号
  -H, --with-filename       print the file name for each match
  -h, --no-filename         suppress the file name prefix on output
      --label=LABEL         use LABEL as the standard input file name prefix
  -o, --only-matching       show only the part of a line matching PATTERN
  			   只显示被模式匹配到的字符串。
  -q, --quiet, --silent     suppress all normal output
      --binary-files=TYPE   assume that binary files are TYPE;
                            TYPE is 'binary', 'text', or 'without-match'
  -a, --text                equivalent to --binary-files=text
  			    不要忽略二进制的数据
  -I                        equivalent to --binary-files=without-match
  -d, --directories=ACTION  how to handle directories;
                            ACTION is 'read', 'recurse', or 'skip'
  -D, --devices=ACTION      how to handle devices, FIFOs and sockets;
                            ACTION is 'read' or 'skip'
  -r, --recursive           like --directories=recurse
  			    在多级目录中对文本进行递归搜索	
  -R, --dereference-recursive
                            likewise, but follow all symlinks
      --include=FILE_PATTERN
                            search only files that match FILE_PATTERN
      --exclude=FILE_PATTERN
                            skip files and directories matching FILE_PATTERN
      --exclude-from=FILE   skip files matching any file pattern from FILE
      --exclude-dir=PATTERN directories that match PATTERN will be skipped.
  -L, --files-without-match print only names of FILEs containing no match
  -l, --files-with-matches  print only names of FILEs containing matches
  -c, --count               print only a count of matching lines per FILE
  			   显示总共有多少行被匹配到了，而不是显示被匹配到的内容，注意如果同时使用-cv选项是显示有多少行没有被匹配到。
  -T, --initial-tab         make tabs line up (if needed)
  -Z, --null                print 0 byte after FILE name

Context control:
  -B, --before-context=NUM  print NUM lines of leading context
  			    显示匹配到的字符串所在的行及其前n行，before
  -A, --after-context=NUM   print NUM lines of trailing context
                            显示匹配到的字符串所在的行及其后n行，after
  -C, --context=NUM         print NUM lines of output context
  			   显示匹配到的字符串所在的行及其前后各n行，context
  -NUM                      same as --context=NUM
      --group-separator=SEP use SEP as a group separator
      --no-group-separator  use empty string as a group separator
      --color[=WHEN],
      --colour[=WHEN]       use markers to highlight the matching strings;
                            WHEN is 'always', 'never', or 'auto'
  -U, --binary              do not strip CR characters at EOL (MSDOS/Windows)
  -u, --unix-byte-offsets   report offsets as if CRs were not there
                            (MSDOS/Windows)

'egrep' means 'grep -E'.  'fgrep' means 'grep -F'.
```

# sort
```text
Usage: sort [OPTION]... [FILE]...
  or:  sort [OPTION]... --files0-from=F
Ordering options:

  -b, --ignore-leading-blanks  ignore leading blanks
  -d, --dictionary-order      consider only blanks and alphanumeric characters
  -f, --ignore-case           fold lower case to upper case characters
  -g, --general-numeric-sort  compare according to general numerical value
  -i, --ignore-nonprinting    consider only printable characters
  -M, --month-sort            compare (unknown) < 'JAN' < ... < 'DEC'
  -h, --human-numeric-sort    compare human readable numbers (e.g., 2K 1G)
  -n, --numeric-sort          compare according to string numerical value
  			      依照数值的大小排序
  -R, --random-sort           sort by random hash of keys
      --random-source=FILE    get random bytes from FILE
  -r, --reverse               reverse the result of comparisons
      --sort=WORD             sort according to WORD:
                                general-numeric -g, human-numeric -h, month -M,
                                numeric -n, random -R, version -V
				以相反的顺序来排序
  -V, --version-sort          natural sort of (version) numbers within text

Other options:

      --batch-size=NMERGE   merge at most NMERGE inputs at once;
                            for more use temp files
  -c, --check, --check=diagnose-first  check for sorted input; do not sort
  -C, --check=quiet, --check=silent  like -c, but do not report first bad line
      --compress-program=PROG  compress temporaries with PROG;
                              decompress them with PROG -d
      --debug               annotate the part of the line used to sort,
                              and warn about questionable usage to stderr
      --files0-from=F       read input from the files specified by
                            NUL-terminated names in file F;
                            If F is - then read names from standard input
  -k, --key=KEYDEF          sort via a key; KEYDEF gives location and type
  -m, --merge               merge already sorted files; do not sort
  -o, --output=FILE         write result to FILE instead of standard output
  		           将排序后的结果存入指定的文件
  -s, --stable              stabilize sort by disabling last-resort comparison
  -S, --buffer-size=SIZE    use SIZE for main memory buffer
  -t, --field-separator=SEP  use SEP instead of non-blank to blank transition
  			    sort -n -k 2 -t'-' date
			     -t<分隔字符>   指定排序时所用的栏位分隔字符。  -k  选择以哪个区间进行
  -T, --temporary-directory=DIR  use DIR for temporaries, not $TMPDIR or /tmp;
                              multiple options specify multiple directories
      --parallel=N          change the number of sorts run concurrently to N
  -u, --unique              with -c, check for strict ordering;
                              without -c, output only the first of an equal run
			    sort的-u 选项它的作用很简单，就是在输出行中去除重复行
  -z, --zero-terminated     end lines with 0 byte, not newline
      --help     display this help and exit
      --version  output version information and exit

```
# find 
```text
Usage: find [-H] [-L] [-P] [-Olevel] [-D help|tree|search|stat|rates|opt|exec] [path...] [expression]
参考地址：
https://www.cnblogs.com/shenqidu/p/10615593.html

stat filename
查看这三种时间
atime	access time	访问时间	文件中的数据库最后被访问的时间
mtime	modify time	修改时间	文件内容被修改的最后时间
ctime	change time	变化时间	文件的元数据发生变化。比如权限，所有者等
```

# exec
```text
https://www.cnblogs.com/xiaofeiIDO/p/7301327.html
```
