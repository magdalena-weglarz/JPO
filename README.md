# JPO
brylaSim.java
public class brylaSim {
public static void main(String[] args) {
//Inicjacja obiektow
punktM A=new punktM();
punktM B=new punktM(100);
punktM[] E=new punktM[11];
for (int i=0;i<=10;i++) //Petla, ktora generuje tablice obiektów
{
E[i]=new punktM(10+i);
};
A.setMass(50);
//Komunikaty:
System.out.println("A to: "+A+". Masa A wynosi "+A.getMass()+", a moment bezwladnosci "+A.moment()+". B to: "+B+". Masa B wynosi "+B.getMass()+", a moment bezwladnosci "+B.moment());
System.out.println("Moment bezwladnosci A wgledem osi rownoleglej o 10 wynosi "+A.momentSteiner(10));
for (int i=0;i<=10;i++)
{
System.out.println("Masa punktu E["+i+"] wynosi "+E[i].getMass()+", glowny moment bezwladnosci wynosi "+E[i].moment()+", a moment bezwladnosci wzgledem osi odległej o 5 wynosi "+E[i].momentSteiner(5)+". Opis obiektu to: "+E[i]);
};
}
}
punktM.java
public class punktM {
//pola
private double mass;
//konstruktory
public punktM (){mass=0;};//konstruktor domyslny
public punktM (double mass)//konstruktor zwykly (blokuje nadanie ujemnej masy)
{
if (mass>0)
{
this.mass=mass;
}
else
{
this.mass=0;
}
}
//akcesory
public double getMass(){return mass;}//akcesor czytajacy
public void setMass(double mass) //akcesor piszacy (blokuje nadanie ujemnej masy)
{
if (mass>0)
{
this.mass=mass;
}
else
{
this.mass=0;
}
}
//metody
public double moment(){return 0;}//Obliczanie momentu bezwladnosci
public double momentSteiner(float a){return moment()+mass*a*a;}//Obliczanie momentu bezwladnosci z twierdzenia Steinera
public String toString(){return "Punkt Materialny";}//opis obiektu
}
