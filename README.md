#include <time.h>

#include <stdlib.h>

#include <stdio.h>

#include <stdio.h> 

#define S3 "<<★<<★★>>★>>★欢迎购买彩票★<<★<<★★>>★>>"

int num=1000,winNum=0;

void jiemian();

void inputNum();

void showNum();

void showWinNum();

void showResult();

void main()

{

jiemian();

}

void jiemian()

{

int n=0;

system("color 4a");

do{

printf("\n\n%s\n\n",S3);

printf("%20s☆★<<黄山学院15软件工程>>★☆\n\n"," ");

printf(" %100s★★购彩需知★★\n\n"," ");

printf("%20s☆★ 1 不能输入字母★☆\n\n"," ");

printf("%20s☆★ 2 输入三位的正整数★☆\n\n"," ");

printf("%20s☆★ 3 谢谢合作!★☆\n\n"," ");

printf("%100s☆ 开发程序成员 ★孙芹★☆\n\n"," ");

printf("%20s☆★ 自动化购买彩票★☆\n\n"," ");

printf("%20s1： ●★购买彩票●★\n"," ");

printf("%20s2： ●★显示购买的彩票号码★●\n"," ");

printf("%20s3： ●★显示彩票中奖号码★●\n"," ");

printf("%20s4： ●★输出中奖与否★●\n"," ");

printf("%20s5： ●☆退出系统☆●\n"," ");

printf("★☆输入选项代码☆★:");

scanf("%d",&n);

if(n!=1&&n!=2&&n!=3&&n!=4&&n!=5)

printf("★对不起★！★您的输入有误★，★请重新输入★：");

}while(n!=1&&n!=2&&n!=3&&n!=4&&n!=5);

switch(n)

{

case 1:inputNum();break;

case 2:showNum();break;

case 3:showWinNum();break;

case 4:showResult();break;

case 5:printf("★●★★★★★●谢谢使用，欢迎下次再来!★●★★★★★●\n");break;

}

}

void inputNum()/*输入购买彩票的数*/

{

do{

if(num>=100&&num<=1000)

printf("★请输入您要购买的彩票号码★:");

else if(num<100||num>1000)

printf("★对不起★，★您输入的彩票号码有误★.★请重新输入一个新的三位正整数彩票号码★:");

scanf("%d",&num);

}while(num<100||num>=1000);

printf("★您已经成功购买了号码为%d的彩票,请继续选择其它服务★\n",num);

jiemian();

}

void showNum()/*显示购买的彩票号码*/

{

if(num==0)

printf("★对不起★，★您还没有购买任何彩票★\n");

else

printf("★尊敬的用户★，★您购买的彩票号码为%d★\n",num);

jiemian();

}

void showWinNum()/*显示对奖的号数*/

{ srand((unsigned)time( NULL ));

winNum=rand()%(1000-100)+100;

printf("彩票中奖号码为%d\n",winNum);

jiemian();

}

void showResult()/*输出中几等奖*/

{

int numhundred,numten,numgewei,hundred,ten,gewei;//分别表示购买彩票号码和中奖号码的百位，十位，个位

numhundred=num/100;numten=(num-numhundred*100)/10;numgewei=num-numhundred*100-numten*10;

hundred=winNum/100;ten=(winNum-hundred*100)/10;gewei

=winNum-hundred*100-ten*10;

if(numhundred==hundred&&numten==ten&&numgewei==gewei)

printf("★恭喜您中了一等奖，奖金是10000元★。欢迎下次再继续购买!\n");

else if((numhundred==hundred&&numten==ten&&numgewei!=gewei)||(numhundred==hundred&&numten!=ten&&numgewei==gewei)||(numhundred!=hundred&&numten==ten&&numgewei==gewei))

printf("★恭喜您中了二等奖，奖金是5000元★。欢迎下次再继续购买!\n");

else if((numhundred==hundred&&numten!=ten&&numgewei!=gewei)||(numhundred!=hundred&&numten==ten&&numgewei!=gewei)||(numhundred!=hundred&&numten!=ten&&numgewei==gewei))

printf("★恭喜您中了三等奖，奖金是1000元★。欢迎下次再继续购买!\n");

else

printf("★谢谢惠顾，欢迎下次购买!★\n");

jiemian();

} 
