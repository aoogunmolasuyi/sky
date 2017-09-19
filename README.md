include <stdlib.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */
void func(double cost, double paid, int *twenties, int *tens, int *fives, int *ones, int *quarters, int *dimes, int *nickles, int *pennies);
int main(void) {
	double cost=199.95;
	double paid=347.38;
	int twenties,tens,fives,ones,quarters,dimes,nickels,pennies;
	func(cost,paid,&twenties,&tens,&fives,&ones,&quarters,&dimes,&nickels,&pennies);
	printf("%d%d%d%d%d%d%d%d",twenties,tens,fives,ones,quarters,dimes,nickels,pennies);
	return 0;
}
void func(double cost, double paid, int *twenties, int *tens, int *fives, int *ones, int *quarters, int *dimes, int *nickles, int *pennies)
{
	double change, new_change, coins;
	change=paid-cost;
	*twenties=(int)change/20;
	new_change=change-20.0*(double)*twenties;
	*tens=(int)new_change/10;
	change=new_change-10.0*(double)*tens;
	*fives=(int)change/5;
	new_change=change-5.0*(double)*fives;
	*ones=(int)new_change;
	change=new_change-(double)*ones;
	coins=(int)(100*change);
	*quarters=coins/25;
	coins=coins-25**quarters;
	*dimes=coins/10;
	coins=coins-10**dimes;
	*nickles=coins/5;
	*pennies=coins-5**nickles;
}
