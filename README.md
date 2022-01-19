# dsa6
#Character Shifting 

import java.io.*;
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		
		String str="abcd:1234,bcdgfhf:127836,sdjks:1245";
		ArrayList<String>name=new ArrayList<>();
		ArrayList<String>code=new ArrayList<>();
		String output="";
		for(String s:str.split(","))
		{
		    String arr[]=s.split(":");
		    name.add(arr[0]);
		    code.add(arr[1]);
		}
		for(int i=0;i<name.size();i++)
		{
		    String a=name.get(i);
		    String b=code.get(i);
		    int sum=0;
		    for(String find:b.split(""))
		    {
		        int num=Integer.parseInt(find);
		        sum+=(num*num);
		    }
		    if(sum%2==0)
		    {
		       String ans1=a.substring(a.length()-2,a.length());
		       String ans2=a.substring(0,a.length()-2);
		       output+=ans1+ans2+" ";
		    }
		    else
		    {
		    String ans1=a.substring(1,a.length());
		    output+=ans1+a.charAt(0)+" ";
		    }
		}
		System.out.println(output);
	}
}
o/p:-cdab cdgfhfb kssdj
