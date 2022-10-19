# TIL
/*
 * 학생번호,이름,국어,수학점수를 입력받아 총점,평균,학점을 구해서 출력해 보세요.
 * 학생정보는 클래스로 만든다.
 * 학생수는 3명 -> 객체를 배열로 만든다. (10:50)
 * 
 * 평균 90이상 A
 *     80이상 B
 *     ..
 */
 package day07;

import java.util.Scanner;
class MyStudent{
	private int num;
	private String name;
	private int kor;
	private int math;
	private int tot;
	private double ave;
	public MyStudent() {}
	public void input() {
		Scanner scan=new Scanner(System.in);
		System.out.println("학생번호");
		num=scan.nextInt();
		System.out.println("학생이름");
		name=scan.next();
		System.out.println("국어점수");
		kor=scan.nextInt();
		System.out.println("수학점수");
		math=scan.nextInt();
		tot=kor+math;
		ave=tot/1.0;
	}
	public char getGrade() { //이 부분은 몰랐던부분
		if(ave>=90) {
			return 'A';
		}else if(ave>=80) {
			return 'B';
		}else if(ave>=70) {
			return 'C';
		}else {
			return 'F';
		}
	}
	public void printData() {
		System.out.println("학생번호:" + num);
		System.out.println("이름:" + name);
		System.out.println("국어점수:" + kor);
		System.out.println("수학점수:" + math);
		System.out.println("총점:" + tot);
		System.out.println("평균:" +  ave);
		System.out.println("학점:" + getGrade());
	}
}
public class Test03_Quiz {
	public static void main(String[] args) {
		MyStudent[] ms=new MyStudent[3];
		for(int i=0;i<ms.length;i++) {
			ms[i]=new MyStudent();
			ms[i].input();		
		}
		System.out.println("<< 입력된 학생 성적 >>");
		for(int i=0;i<ms.length;i++) {
			ms[i].printData();
		}
	}
}
