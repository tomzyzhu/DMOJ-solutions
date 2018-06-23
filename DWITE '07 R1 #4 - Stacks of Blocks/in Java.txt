import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Stacks {
	public static void main(String[] args) {
		BufferedReader in = new BufferedReader(new InputStreamReader(System.in));

		try {
			int h = Integer.parseInt(in.readLine());
			int b = Integer.parseInt(in.readLine());
			int [] c = new int [101];
			for(int i = 0 ; i < 101 ; i ++) {
				c [i] = 100000;
			}
			c[0] = 0;
			

			for(int i = 0 ; i < b; i ++) {
				int block = Integer.parseInt(in.readLine());
				for(int i2 = 100 ; i2 >=block ; i2--) {
					c[i2] = Math.min(c[i2], c[i2-block]+1);
					//System.out.println(c[i2] + " " + i2);
				}
			}
			if(c[h]!=100000) {
				System.out.println(c[h]);
			}else {
				System.out.println(0);
			}

		}catch(Exception e) {
			e.printStackTrace();
		}
	}
}