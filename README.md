# Vehicle-rental-system-java-mini-project
package java_mini_project;

import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.awt.Font;
import javax.swing.Box;
import javax.swing.SwingConstants;
import javax.swing.JToggleButton;
import javax.swing.JTextField;

public class Demo extends JFrame {

	private static final long serialVersionUID = 1L;
	private JPanel contentPane;
	/**
	 * @wbp.nonvisual location=2,-4
	 */
	private final JPanel panel = new JPanel();
	private JTextField txtname;
	private JTextField txtdays;
	private JTextField txtvname;
	JLabel lblotp;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Demo frame = new Demo();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public Demo() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 893, 715);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));

		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		Box verticalBox = Box.createVerticalBox();
		verticalBox.setBounds(292, 29, 0, 0);
		contentPane.add(verticalBox);
		
		JLabel lblNewLabel = new JLabel("VEHICLE RENTAL SYSTEM");
		lblNewLabel.setBounds(297, 10, 295, 38);
		lblNewLabel.setFont(new Font("Yu Gothic", Font.ITALIC, 23));
		contentPane.add(lblNewLabel);
		
		JLabel lblNewLabel_1 = new JLabel("New label");
		lblNewLabel_1.setBounds(87, 41, 0, 13);
		contentPane.add(lblNewLabel_1);
		
		JLabel lblvehicle = new JLabel("VEHICLES AVAILABLE");
		lblvehicle.setFont(new Font("Tahoma", Font.PLAIN, 20));
		lblvehicle.setBounds(29, 55, 255, 50);
		contentPane.add(lblvehicle);
		
		JLabel lblv1 = new JLabel("1  Toyota Corolla");
		lblv1.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblv1.setBounds(40, 102, 165, 50);
		contentPane.add(lblv1);
		
		JLabel lblv2 = new JLabel("2  Honda Civic");
		lblv2.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblv2.setBounds(40, 162, 173, 58);
		contentPane.add(lblv2);
		
		JLabel lblv3 = new JLabel("3  Ford Mustang");
		lblv3.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblv3.setBounds(40, 230, 180, 58);
		contentPane.add(lblv3);
		
		JLabel lblprice = new JLabel("PRICE PER DAY");
		lblprice.setFont(new Font("Tahoma", Font.PLAIN, 20));
		lblprice.setBounds(307, 58, 185, 38);
		contentPane.add(lblprice);
		
		JLabel lblp1 = new JLabel("$50.0/day");
		lblp1.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblp1.setBounds(345, 102, 247, 50);
		contentPane.add(lblp1);
		
		JLabel lblp2 = new JLabel("$60.0/day");
		lblp2.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblp2.setBounds(345, 172, 261, 38);
		contentPane.add(lblp2);
		
		JLabel lblp3 = new JLabel("$100.0/day");
		lblp3.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblp3.setBounds(343, 240, 258, 38);
		contentPane.add(lblp3);
		
		JLabel lblvname = new JLabel("Enter the vehicle name");
		lblvname.setFont(new Font("Tahoma", Font.PLAIN, 20));
		lblvname.setBounds(40, 460, 238, 58);
		contentPane.add(lblvname);
		
		txtname = new JTextField();
		txtname.setBounds(338, 320, 357, 50);
		contentPane.add(txtname);
		txtname.setColumns(10);
		
		
		JLabel lbldays = new JLabel("Enter the number of days");
		lbldays.setFont(new Font("Tahoma", Font.PLAIN, 20));
		lbldays.setBounds(50, 369, 255, 81);
		contentPane.add(lbldays);
		
		txtdays = new JTextField();
		txtdays.setBounds(345, 387, 347, 50);
		contentPane.add(txtdays);
		txtdays.setColumns(10);
		
		JLabel lblname = new JLabel("Enter the name");
		lblname.setFont(new Font("Tahoma", Font.PLAIN, 20));
		lblname.setBounds(50, 321, 230, 38);
		contentPane.add(lblname);
		
		txtvname = new JTextField();
		txtvname.setBounds(345, 468, 347, 50);
		contentPane.add(txtvname);
		txtvname.setColumns(10);
		
		JButton btnok = new JButton("OK");
		btnok.addActionListener(new ActionListener() {
		    public void actionPerformed(ActionEvent e) {
		        String n = txtname.getText();
		        String v = txtvname.getText();
		        int days;

		        try {
		            days = Integer.parseInt(txtdays.getText());
		        } catch (NumberFormatException ex) {
		            lblotp.setText("Please enter a valid number of days!");
		            return;
		        }

		        double cost = 0.0;

		        if (v.equalsIgnoreCase("Toyota Corolla")) {
		            cost = days * 50.0;
		        } else if (v.equalsIgnoreCase("Honda Civic")) {
		            cost = days * 60.0;
		        } else if (v.equalsIgnoreCase("Ford Mustang")) {
		            cost = days * 100.0;
		        } else {
		            lblotp.setText("Invalid vehicle name. Please try again!");
		            return;
		        }

		        lblotp.setText(n + ", your total cost is: $" + cost);
		    }
		});

		btnok.setFont(new Font("Tahoma", Font.PLAIN, 23));
		btnok.setBounds(29, 533, 148, 50);
		contentPane.add(btnok);
		
		
		JButton btnreturn = new JButton("RETURN");
		btnreturn.addActionListener(new ActionListener() {
		    public void actionPerformed(ActionEvent e) {
		        String name = txtname.getText();
		        String vehicle = txtvname.getText();

		        // Validation to ensure name and vehicle are filled
		        if (name.isEmpty() || vehicle.isEmpty()) {
		            lblotp.setText("Please enter the name and vehicle to return!");
		        } else {
		            lblotp.setText("Vehicle " + vehicle + " has been successfully returned by " + name + "!");
		            
		            // Clear fields to simulate the vehicle return process
		            txtname.setText("");
		            txtdays.setText("");
		            txtvname.setText("");
		        }
		    }
		});

		btnreturn.setFont(new Font("Tahoma", Font.PLAIN, 23));
		btnreturn.setBounds(198, 533, 120, 50);
		contentPane.add(btnreturn);
		
		JButton btnreset = new JButton("RESET");
		btnreset.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				txtname.setText(" ");
				txtdays.setText(" ");
				txtvname.setText(" ");
				lblotp.setText(" ");
				}
		});
		btnreset.setFont(new Font("Tahoma", Font.PLAIN, 23));
		btnreset.setBounds(29, 608, 148, 38);
		contentPane.add(btnreset);
		
		lblotp = new JLabel("");
		lblotp.setBounds(343, 557, 479, 89);
		contentPane.add(lblotp);
	}
}
