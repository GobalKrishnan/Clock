# Clock
program  in java

import javax.swing.ImageIcon; <br>
import javax.swing.JFrame;<br>
import javax.swing.UIManager;<br>
import javax.swing.UnsupportedLookAndFeelException;<br>

import gki.clock.CircleClock;<br>
import gki.clock.ClockListener;<br>

public class Test extends JFrame{ <br>
   public Test(){ <br>
	   
	   
	    CircleClock c=new CircleClock();<br>
	    c.setRadius(150);<br>
	    c.setLocation(0,100);<br>
	    
	   
	    add(c);<br>
	    
	    c.addClockListener(new ClockListener() {<br>
			
			@Override<br>
			public void time(int hour, int minute, int second, int milliSecond, String period) {<br>
				// TODO Auto-generated method stub<br>
				System.out.println(hour+":"+minute+":"+second+":"+milliSecond+" "+period);<br>

			}<br>

			@Override<br>
			public void alarm(boolean a) {<br>
				// TODO Auto-generated method stub<br>
				System.out.println(a);<br>
			}<br>
			
			
		});<br>
	    
	    setVisible(true);<br>
    	setIconImage(new ImageIcon(getClass().getResource("/gki/clock/logo.png")).getImage());<br>
        setTitle("Gobal Krishnan V");<br>
	    setDefaultCloseOperation(EXIT_ON_CLOSE);<br>
	    setSize(500,500);<br>
   }<br>
	public static void main(String[] args) {<br>
		// TODO Auto-generated method stub<br>
      
		try {<br>
			UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());<br>
		} catch (ClassNotFoundException | InstantiationException | IllegalAccessException<br>
				| UnsupportedLookAndFeelException e) {<br>
			// TODO Auto-generated catch block<br>
			e.printStackTrace();<br>
		}<br>
		new Test();<br>
	}<br>

}<br>
