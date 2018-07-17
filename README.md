import javax.swing.*;
import java.awt.*;
import java.awt.event.*; 

class Calculator extends JFrame implements ActionListener{

	Double i,j;
	JPanel p;
	JLabel l1,l2,l3;
	JTextField t1,t2,t3;
	JButton b1,b2,b3,b4;
 
 public Calculator(){
	
		super("mmu");
		p=new JPanel();
	//	p.setLayout(null);
		l1=new JLabel("number 1");
		l2=new JLabel("number 2");
		b1=new JButton("+");
		b2=new JButton("-");
		b3=new JButton("/");
		b4=new JButton("*");

		l3=new JLabel("Result");
		
		t1=new JTextField(10);
		
		t2=new JTextField(10);
		 
		t3=new JTextField(10);
		getContentPane().add(p);
		/*l1.setBounds(50,70,90,30);
		t1.setBounds(80,70,150,30);
		l2.setBounds(50,60,90,30);
		t2.setBounds(80,60,150,30);
		b1.setBounds(50,50,150,30);
		b2.setBounds(55,50,150,30);
		b3.setBounds(60,50,150,30);
		b4.setBounds(70,50,150,30);
		l3.setBounds(50,40,90,30);
		t3.setBounds(80,40,150,30);*/


		b1.addActionListener(this);
		 b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
		p.add(l1);
		p.add(t1);
		p.add(l2);
		p.add(t2);
		p.add(b1);
		p.add(b2);
		p.add(b3);
		p.add(b4);
		p.add(l3);
		p.add(t3);
		setSize(300,300);
		setVisible(true);
		setLocation(400,200);
		
	}
	
	
		public void actionPerformed(ActionEvent evt){
		
			try{
			
		
		 i=Double.parseDouble(t1.getText());
			
		 j=Double.parseDouble(t2.getText());
		}catch(Exception e){
		
			JOptionPane.showMessageDialog(this,"please enter number");
		}
			if(evt.getSource()==b1) {
				
			Double add=i+j;
			
			String s=String.valueOf(add);
		 	t3.setText(s);	
		 	}

			if(evt.getSource()==b2) {
				
			Double sub=i-j;
			
			String s1=String.valueOf(sub);
		 	t3.setText(s1);
		 }
		 if(evt.getSource()==b3){
		 
		 	try{
		 	double div=i/j;
		 	String s2=String.valueOf(div);
		 	t3.setText(s2);
		 	if(j==0)
		 		throw new Exception();
		 } catch(Exception e){
		 
		 	JOptionPane.showMessageDialog(this,"0 cannot be divide");
		 }	
		}
		if(evt.getSource()==b4)
		{
			double mult=i*j;
			String s3=String.valueOf(mult);
			t3.setText(s3);
		}
	}
	
	public static void main(String[] args) {
		new Calculator();
	}


}
