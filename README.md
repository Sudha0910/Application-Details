# Application-Details
#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<stdlib.h>

struct ApplicationDetails{
	char appname[20];
	char author[20];
	int year,price,version;
}t;
void main(){
	struct ApplicationDetails a[20];
	char ans;
	char temp[40];
	int num,i,choice,j,temp1;
	printf("Enter the number of application:");
	scanf("%d",&num);
	printf("\n");
	for(i=0;i<num;i++){
		printf("______APPLICATION DETAILS_____");
		printf("\n Enter the application name:");
		scanf("%s",&a[i].appname);
		printf("\n Enter the author of application:");
		scanf("%s",&a[i].author);
		printf("\n Enter the published year of application:");
		scanf("%d",&a[i].year);
		printf("\n Enter the version of application:");
		scanf("%d",&a[i].version);
		printf("\n Enter the price of the application:");
		scanf("%d",&a[i].price);
	}
	do{
	clrscr();
	printf("\n __________MAIN MENU__________");
	printf("\n1.Display all the detail of the application by a given author");
	printf("\n2.sort the detail in increasing order of price");
	printf("\n3.display the detail published by publisher in a given year");
	printf("\n4.sort the details by author and publishing year");
	printf("\n5.EXIT");
	printf("\n Enter your choice:");
	scanf("%d",&choice);
	switch(choice){
		case 1:
		       printf("Enter the author name:");
		       scanf("%s",&temp);
		       for(i=0;i<num;i++){
		       if(strcmp(a[i].author,temp)==0)
		       {
		       printf("\n%s",a[i].appname);
		       printf("\t%d",a[i].year);
		       printf("\t%d",a[i].version);
		       printf("\t%d",a[i].price);
		       }
		       }
		       break;
		case 2:
		       for(i=0;i<num;i++){
			for(j=0;j<num-1;j++){
			 if(a[j].price>a[j+1].price){
			  t=a[j];
			  a[j]=a[j+1];
			  a[j+1]=t;
			 }
			}
		       }
		       printf("\nDetails of application in order of price");
		       printf("\nApplication\tAuthor_name\tversion\tprice\tyear");
		       printf("\n____________________________________________________________________________");
		       for(i=0;i<num;i++){
			  printf("\n%s\t%s\t%d\t%d\t%d",a[i].appname,a[i].author,a[i].version,a[i].price,a[i].year);
		       }
		       break;
		case 3:
		       printf("Enter the author name");
		       scanf("%s",&temp);
		       printf("Enter the Published year:");
		       scanf("%d",&temp1);
		       for(i=0;i<num;i++){
		       if(strcmp(a[i].author,temp)==0 && a[i].year==temp1){
		       printf("\napplication\tprice\tversion");
		       printf("\n______________________________________________");
		       printf("\n%s\t%d\t%d",a[i].appname,a[i].price,a[i].version);
		       }
		       }
		       break;
		case 4:
		       for(i=0;i<num-1;i++){
			for(j=i+1;j<num;j++){
			 if(strcmp(a[i].author,a[j].author) > 0){
			  t=a[i];
			  a[i]=a[j];
			  a[j]=t;
			  }
			 }
		       }
		       printf("\nList of application sorted by author");
		       printf("\nauthor\tApplication");
		       printf("\n________________________");
		       for(i=0;i<num;i++){
		       printf("\n%s\t%s",a[i].author,a[i].appname);
		       }
		       for(i=0;i<num;i++){
			for(j=i+1;j<num-1;j++){
			 if(a[j].year>a[j+1].year){
			  t=a[j];
			  a[j]=a[j+1];
			  a[j+1]=t;
			 }
			}
		       }
		       printf("\nList of application sorted by Published year");
		       printf("\nyear\tApplication");
		       printf("\n________________________");
		       for(i=0;i<num;i++){
		       printf("\n%d\t%s",a[i].year,a[i].appname);
		       }
		       break;
		case 5:exit(0);

	 }
	printf("\nDo you wish to go to main menu?");
	ans=getch();
	}while(ans=='y'||ans=='Y');
	getch();

}
