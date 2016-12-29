# LXZ_DVD_RENT
dvd renting system by tongxing lijiakai and pantian

//import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.io.BufferedReader;
import java.io.File;
import java.io.FileOutputStream;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.ArrayList;
import javax.swing.JFrame;
import javax.swing.JRadioButton;
import javax.swing.ButtonGroup;
public class DVD_RENTING_SYSTEM {

	//单独代码无法独立运行，需要结合主代码
	
	
	if(e.getSource()==bad_user_inputbutton){
			FileOutputStream fos=null;
			try{
				
				fos=new FileOutputStream("c:\\Temp\\blacklist.txt",true);
		
						String temp=bad_user.getText().trim()+"|"+bad_user_id.getText().trim()+"|";
				
				
						try{
		       fos.write(temp.getBytes());
		    
		       
				}catch(Exception e1){
					e1.printStackTrace();
				}	
				
		       	}catch(Exception ex){
		       		ex.printStackTrace();
		       	}finally{
		       		try{
		       			fos.close();
		       		}catch(Exception ex){
		       			ex.printStackTrace();
		       		}
		       	}
				JOptionPane.showMessageDialog(null,"不良租客："+bad_user.getText()+"|不良租客身份证号："+bad_user_id.getText().trim()+"|","不良租客"
				,JOptionPane.INFORMATION_MESSAGE);
				bad_user.setText("");
				bad_user_id.setText("");
else if(e.getSource()==user_searchbutton){
			File file=new File("c:\\Temp\\rent.txt");
			File file2=new File("c:\\Temp\\blacklist.txt");
			if(!file.exists()||!file2.exists())
			return;
				FileReader fr=null;
				FileReader fr2=null;
		        BufferedReader br=null;
		        BufferedReader br2=null;
		        try{ 
		        	int count=0;
		        	int a = 0;
		        	fr=new FileReader(file);
		        	fr2=new FileReader(file2);
		        	br=new BufferedReader(fr);
		        	br2=new BufferedReader(fr2);
		        	String lineStr=null;
		        	String lineStr2=null;
		           String error=null;
		         while((lineStr=br.readLine())!=null){
		        	String[] info=lineStr.split("\\|");
		        	  while((lineStr2=br2.readLine())!=null){
		        		  String[] info2=lineStr2.split("\\|");
		        		  for(int i=0;i<info2.length;i++){
				        		 if(user.getText().compareTo(info2[i])==0) 
				        		 {
				        			 JOptionPane.showMessageDialog(null,"该客户为不良用户","搜索结果",JOptionPane.INFORMATION_MESSAGE); 
				        		 }
				        	 }
		        	  }
		        	 for(int i=0;i<info.length;i++){
		        		 if(user.getText().compareTo(info[i])==0) 
		        		
		        		 { a=i;break;}
		        		 
		        	 }
		        		 if(user.getText().compareTo(info[a])==0)
		        		 JOptionPane.showMessageDialog(null,"查询成功：姓名："+info[a-1]+"    身份证号："+info[a]+"    在租DVD："+info[a+1]+"   \n 在租DVD编号："+info[a+2]+"    租借月份："+info[a+3]+"    租借日："+info[a+4]+"    支付金额："+info[a+5],"搜索结果",JOptionPane.INFORMATION_MESSAGE);
		        		 
		        	  else 
			        	 JOptionPane.showMessageDialog(null,"该客户无在租DVD","搜索结果",JOptionPane.INFORMATION_MESSAGE); 
			        	
			         
		         }//while((lineStr=br.readLine())==null){
		        	// JOptionPane.showMessageDialog(null,"该客户无在租DVD","搜索结果",JOptionPane.INFORMATION_MESSAGE); break;
		     //    }
		        	
		}catch(Exception ex){
			ex.printStackTrace();
		}finally{
			try{
				br.close();
				fr.close();
			}catch(Exception ex){
				ex.printStackTrace();
			}
         	}
if(e.getSource()==btn){
        	  File file=new File("c:\\Temp\\account.txt");
        	  File file2=new File("c:\\Temp\\password.txt");
  			if(!file.exists()||!file2.exists())
  			return;
  				FileReader fr=null;
  		        BufferedReader br=null;
  		      FileReader fr2=null;
		        BufferedReader br2=null;
  		        try{ 
  		        	
  		        	fr=new FileReader(file);
  		        	fr2=new FileReader(file2);
  		        	br=new BufferedReader(fr);
  		        	br2=new BufferedReader(fr2);
  		        	
  		
  		        		 if(account.getText().compareTo(br.readLine())==0&&password.getText().compareTo(br2.readLine())==0){
  		        			this.getContentPane().add(old_manage);
  		      			this.getContentPane().add(i);
  		      			this.getContentPane().add(search);
  		      			this.getContentPane().add(user_manage);
  		      			this.getContentPane().add(rent1);
  		      			this.getContentPane().add(type_in);
  		      			this.getContentPane().add(return_back);
  		      		    //this.setJMenuBar(menubar);
  		      		    this.remove(account);
  		      	        this.remove(accountlabel);
  		                this.remove(password);
  		                this.remove(passwordlabel);
  		                this.remove(pass);
  		                this.remove(btn);
  		              this.repaint();
  					this.getContentPane().validate();
  		        		 }
  		        	  else{
  			        	 JOptionPane.showMessageDialog(null,"登录失败","提示",JOptionPane.INFORMATION_MESSAGE); 
  			        	
  			         }
  		         
  		        	
  		}catch(Exception ex){
  			ex.printStackTrace();
  		}finally{
  			try{
  				br.close();
  				fr.close();
  			}catch(Exception ex){
  				ex.printStackTrace();
  			}
           	}
        	  
