# regex
```c
//一个最简单的C语言正则表达式使用例子(不含错误等检测)
//注意，正则不在标准的C中，此处是Linux提供的库
//man regex 获取更多信息，正则表达式规范为POSIX regex
#include <stddef.h>
#include <sys/types.h>
#include <regex.h>
#include <stdio.h>

int main(){
	char input[256];
	regex_t regex;
	regmatch_t pmatch[1];
	//将正则表达式字符串(第二个参)，编译给regex，之后使用regex即代表这个正则表达式
	regcomp(&regex,"a[a-z]c",REG_EXTENDED);

	scanf("%s",input);
	//寻找input中符合regex正则的第一个匹配项，保存到pmatch中
	//pmatch[0].rm_so为匹配项的起始索引，rm_eo为结束索引
	int ret=regexec(&regex,input,1,pmatch,0);

	if(ret==_REG_NOMATCH){
		printf("there is no match in input string\n");
		return 0;
	}

	printf("%d %d\n",pmatch[0].rm_so,pmatch[0].rm_eo);
	for(int j=pmatch[0].rm_so;j<pmatch[0].rm_eo;++j){
		printf("%c",input[j]);
	}
	printf("\n");

	//free正则串
	regfree(&regex);
	
	return 0;
}
```
