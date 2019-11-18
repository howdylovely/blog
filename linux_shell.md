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
