# Assignment-2

### MyFrame_1 (GUI)

~~~
// Java program to implement 
// a Simple Registration Form  
// using Java Swing 
//Credit to : www.geeksforgeeks.org/java-swing-simple-user-registration-form/
import javax.swing.*; 
import java.awt.*; 
import java.awt.event.*; 

class MyFrame_1 
   extends JFrame 
   implements ActionListener { 

   // Components of the Form 
   private static Container c; 
   private static JLabel title;  
   private static JLabel name;   
   private static JTextField tname;  
   private static JLabel ic; 
   private static JTextField tic; 
   private static JLabel clothes; 
   private static JRadioButton bajuKurung;  
   private static JRadioButton cheongsam; 
   private static JRadioButton sari;  
   private static ButtonGroup gengp;   
   private static JLabel add; 
   private static JTextArea tadd; 
   private static JCheckBox term; 
   private static JButton sub; 
   private static JButton reset; 
   private static JTextArea tout; 
   private static JLabel res; 
   private static JTextArea resadd;  

   // constructor, to initialize the components 
   // with default values. 
   public MyFrame_1() 
   {
      setTitle("Welcome to our Boutique"); 
      setBounds(300, 90, 900, 600); 
      setDefaultCloseOperation(EXIT_ON_CLOSE); 
      setResizable(false); 

      c = getContentPane(); 
      c.setLayout(null); 

      title = new JLabel("Hello ! please fill in"); 
      title.setFont(new Font("Arial", Font.PLAIN, 30)); 
      title.setSize(300, 30); 
      title.setLocation(300, 30); 
      c.add(title); 

      name = new JLabel("Name"); 
      name.setFont(new Font("Arial", Font.PLAIN, 20)); 
      name.setSize(100, 20); 
      name.setLocation(100, 100); 
      c.add(name); 

      tname = new JTextField(); 
      tname.setFont(new Font("Arial", Font.PLAIN, 15)); 
      tname.setSize(190, 20); 
      tname.setLocation(200, 100); 
      c.add(tname); 

      ic = new JLabel("No IC"); 
      ic.setFont(new Font("Arial", Font.PLAIN, 20)); 
      ic.setSize(100, 20); 
      ic.setLocation(100, 150); 
      c.add(ic); 

      tic = new JTextField(); 
      tic.setFont(new Font("Arial", Font.PLAIN, 15)); 
      tic.setSize(150, 20); 
      tic.setLocation(200, 150); 
      c.add(tic); 

      clothes = new JLabel("Clothes"); 
      clothes.setFont(new Font("Arial", Font.PLAIN, 20)); 
      clothes.setSize(100, 20); 
      clothes.setLocation(100, 200); 
      c.add(clothes); 

      bajuKurung = new JRadioButton("Baju Kurung"); 
      bajuKurung.setFont(new Font("Arial", Font.PLAIN, 15)); 
      bajuKurung.setSelected(true); 
      bajuKurung.setSize(150, 20); 
      bajuKurung.setLocation(200, 200); 
      c.add(bajuKurung); 

      cheongsam = new JRadioButton("Cheongsam"); 
      cheongsam.setFont(new Font("Arial", Font.PLAIN, 15)); 
      cheongsam.setSelected(false); 
      cheongsam.setSize(150, 20); 
      cheongsam.setLocation(200, 235); 
      c.add(cheongsam); 
      
      sari = new JRadioButton("Sari"); 
      sari.setFont(new Font("Arial", Font.PLAIN, 15)); 
      sari.setSelected(false); 
      sari.setSize(80, 20); 
      sari.setLocation(200, 265); 
      c.add(sari); 

      gengp = new ButtonGroup(); 
      gengp.add(bajuKurung); 
      gengp.add(cheongsam); 
      gengp.add(sari); 

      add = new JLabel("Address"); 
      add.setFont(new Font("Arial", Font.PLAIN, 20)); 
      add.setSize(100, 20); 
      add.setLocation(100, 300); 
      c.add(add); 

      tadd = new JTextArea(); 
      tadd.setFont(new Font("Arial", Font.PLAIN, 15)); 
      tadd.setSize(200, 75); 
      tadd.setLocation(200, 300); 
      tadd.setLineWrap(true); 
      c.add(tadd); 

      term = new JCheckBox("Accept Terms And Conditions."); 
      term.setFont(new Font("Arial", Font.PLAIN, 15)); 
      term.setSize(250, 20); 
      term.setLocation(150, 400); 
      c.add(term); 

      sub = new JButton("Submit"); 
      sub.setFont(new Font("Arial", Font.PLAIN, 15)); 
      sub.setSize(100, 20); 
      sub.setLocation(150, 450); 
      sub.addActionListener(this); 
      c.add(sub); 

      reset = new JButton("Reset"); 
      reset.setFont(new Font("Arial", Font.PLAIN, 15)); 
      reset.setSize(100, 20); 
      reset.setLocation(270, 450); 
      reset.addActionListener(this); 
      c.add(reset); 

      tout = new JTextArea(); 
      tout.setFont(new Font("Arial", Font.PLAIN, 15)); 
      tout.setSize(300, 400); 
      tout.setLocation(500, 100); 
      tout.setLineWrap(true); 
      tout.setEditable(false);  
      c.add(tout); 

      res = new JLabel(""); 
      res.setFont(new Font("Arial", Font.PLAIN, 20)); 
      res.setSize(500, 25); 
      res.setLocation(100, 500); 
      c.add(res); 

      resadd = new JTextArea(); 
      resadd.setFont(new Font("Arial", Font.PLAIN, 15)); 
      resadd.setSize(200, 75); 
      resadd.setLocation(580, 175); 
      resadd.setLineWrap(true); 
      c.add(resadd); 

      setVisible(true); 
   } 

   // method actionPerformed() 
   // to get the action performed 
   // by the user and act accordingly 
   
   public void actionPerformed(ActionEvent e) 
   { 
      if (e.getSource() == sub) { 
         if (term.isSelected()) { 
            String data2;
            String data = "Name : " + tname.getText() + "\n" + "No IC : " + tic.getText() + "\n";               
            if (bajuKurung.isSelected()){ 
                     data2 = 
                          "\nClothes : "
                          + "Baju Kurung" 
                          + "\n"; 
            }
            else if 
                   (cheongsam.isSelected()){ 
                     data2 =
                      "\nClothes :" 
                      +" Cheongsam" 
                      + "\n"; 
                  }
               else 
                    { 
                      data2 = 
                      "\nClothes :" 
                      + "Sari" 
                      + "\n"; 
                      }

            String data1 = "Address : " + tadd.getText(); 
            tout.setText(data + data1 + data2); 
            tout.setEditable(false); 
            res.setText("Registration Successfully.."); 
         } 
         else { 
            tout.setText(""); 
            resadd.setText(""); 
            res.setText("Please accept the" + " terms & conditions.."); 
         } 
      } 

      else if (e.getSource() == reset) { 
         String def = ""; 
         tname.setText(def); 
         tadd.setText(def); 
         tic.setText(def);
         bajuKurung.setText(def);
         cheongsam.setText(def);
         sari.setText(def);
         res.setText(def); 
         tout.setText(def); 
         term.setSelected(false);  
         resadd.setText(def); 
      } 
   } 
} 

// Driver Code 
class Registration { 

   public static void main(String[] args) throws Exception 
   { 
      MyFrame_1 f = new MyFrame_1(); 
   } 
}
