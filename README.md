
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.UIManager;
import javax.swing.UnsupportedLookAndFeelException;

import gki.clock.CircleClock;
import gki.clock.ClockListener;

public class Test extends JFrame{
   public Test(){
	   
	   
	    CircleClock c=new CircleClock();
	    c.setRadius(150);
	    c.setLocation(0,100);
	    
	   
	    add(c);
	    
	    c.addClockListener(new ClockListener() {
			
			@Override
			public void time(int hour, int minute, int second, int milliSecond, String period) {
				// TODO Auto-generated method stub
				System.out.println(hour+":"+minute+":"+second+":"+milliSecond+" "+period);

			}

			@Override
			public void alarm(boolean a) {
				// TODO Auto-generated method stub
				System.out.println(a);
			}
			
			
		});
	    
	    setVisible(true);
    	setIconImage(new ImageIcon(getClass().getResource("/gki/clock/logo.png")).getImage());
        setTitle("Gobal Krishnan V");
	    setDefaultCloseOperation(EXIT_ON_CLOSE);
	    setSize(500,500);
   }
	public static void main(String[] args) {
		// TODO Auto-generated method stub
      
		try {
			UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());
		} catch (ClassNotFoundException | InstantiationException | IllegalAccessException
				| UnsupportedLookAndFeelException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		new Test();
	}

}
