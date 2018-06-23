import java.io.BufferedReader;
import java.io.InputStreamReader;


public class Primes {

	public static int n;
	public static long f;
	public static String [] t; 

	public static long gcd(long a, long b){
		if(a == 0)
			return b;
		return gcd(b%a, a);
	}

	public static long prime (long check){
		int temp = 0;
		Exit2:{
		do{
			Exit1:{
			//System.out.println("checking " + check + " max limit is " +(int)(Math.ceil(Math.sqrt(check))));
			if(check == 2)
				break Exit2;
			else
			for(temp =2; temp <= (int)(Math.ceil(Math.sqrt(check))); temp ++){
				if(check%temp == 0)
					break Exit1;
			}
			break Exit2;
			}
			//System.out.println("found temp " + temp);
			check = check/temp;
		}while (true);
		}
		return check;
	}
	public static void main(String[] args) {
		BufferedReader in = new BufferedReader (new InputStreamReader (System.in));

//		for(long i = 1; i < 1000000; i ++){
//			System.out.println(i+" "+ prime(i));
//		}
		try{
			n = Integer.parseInt(in.readLine());
			t = in.readLine().split(" " );
			f = Long.parseLong(t[0]);
			if(n>1){
			for(int i = 1 ; i < n ; i ++){
				long a = Long.parseLong(t[i]);
				f = gcd(Math.min(f, a), Math.max(f, a));
			}
			}
			//System.out.println(f);

			f = prime(f);
			if(f!= 1)
				System.out.println(f);
			else
				System.out.println("DNE");


		}catch(Exception e){
			e.printStackTrace();
		}
	}
}