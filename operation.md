# operation2
import java.util.*;
public class Operation{
	float num1=0;
	float num2=0;
	public static void main(String[] args){
		Scanner snc=new Scanner(System.in);int cont=1;
		do {
		System.out.println("Enter a Expression:");
		String exp=snc.next();
		Operation op=new Operation();
		int flag=0;
		char operator='\0';

		for(int i=0;i<exp.length();i++)
		{ 	
			if(Character.isDigit(exp.charAt(i))){
				if(flag==0)
					op.setNum1(exp.charAt(i));
				if(flag==1) 
					op.setNum2(exp.charAt(i));
				
			}
			else{
				flag=1;
				operator=exp.charAt(i);
			}
		}

		System.out.println("num1="+op.num1);
		System.out.println("num2="+op.num2);
		op.compute(operator);

		System.out.println("Press 1 to continue/ Press 0 to exit");
		cont =snc.nextInt();
		}
		while(cont!=0);
	  
	}
	
	void compute(char op){
		switch(op){
			case '+':addition();
				 break;
			case '-':subtraction();
				 break;
			case '*':multiplication();
				 break;
			case '/':division();
				 break;
			default:System.out.println("Invalid");
		}				
	}

	void setNum1(char ex){
		num1=(num1*10)+(ex-'0');
	}
	void setNum2(char ex){
		num2=(num2*10)+(ex-'0');
	}

	float getNum1(){
		return num1;
	}
	float getNum2(){
		return num2;
	}

	void addition(){
		System.out.println("Operation=Addition");
		float resa=getNum1()+getNum2();
		System.out.println("Result="+resa);
	}

	void subtraction(){	
		System.out.println("Operation=Subtraction");
		float resm=getNum1()-getNum2();
		System.out.println("Result="+ resm);
	}

	void multiplication(){	
		System.out.println("Operation=Multiplication");
		float resm=getNum1()*getNum2();
		System.out.println("Result="+ resm);
	}

	void division(){	
		System.out.println("Operation=Division");
		try{
			
			float resl=num1/num2;
			
			System.out.println("Result="+ resl);
			
		}
		catch(Exception e) {
			System.out.println(e);
		}
		
	}
}
