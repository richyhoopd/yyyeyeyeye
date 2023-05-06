# yyyeyeyeye
olmos


// Emula a una calculadora simple ...

import java.io.*;
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

public class Calculadora extends JFrame
{
	JPanel JP = new JPanel();
	JTextField JTF1=null, JTF2=null;
	JLabel Mas, Resp;
	JButton Igual, Limpiar;

	public static void main(String R[]) { new Calculadora(); }

	public Calculadora()
	{

		this.setBounds(100, 100, 500, 500);
		setVisible(true);

		JP.setLayout(null);	// soy duenio de todo
		JP.setBackground(Color.blue);
		JP.setBounds(10, 10, 400, 400);
		add(JP);

		JTF1 = new JTextField(); JTF1.setBounds( 10, 100, 50, 40);
		JP.add(JTF1); JTF1.setBackground(Color.yellow);
		JTF2 = new JTextField(); JTF2.setBounds(110, 100, 50, 40);
		JP.add(JTF2); JTF2.setBackground(Color.yellow);

		Mas = new JLabel("+", Mas.CENTER); Mas.setBounds(65, 100, 30, 40); JP.add(Mas);
			Mas.setForeground(Color.green); Mas.setBackground(Color.yellow);
		Resp= new JLabel("----------", Resp.CENTER); Resp.setBounds(260, 100, 50, 40);
			JP.add(Resp); Resp.setForeground(Color.green); Resp.setBackground(Color.yellow);

		Igual = new JButton("="); Igual.setBounds(190, 100, 50, 40); JP.add(Igual);
			Igual.setForeground(Color.green); Igual.setBackground(Color.yellow);
			Igual.addActionListener(new Evento());
		Limpiar=new JButton("Limpiar"); Limpiar.setBounds(70, 150, 100, 40); JP.add(Limpiar);
			Limpiar.setForeground(Color.green); Limpiar.setBackground(Color.yellow);
			Limpiar.addActionListener(new Evento());
	}		// FIN DEL METODO CONSTRUCTOR

	class Evento implements ActionListener
	{
		public void actionPerformed(ActionEvent DATOS)
		{
			String Boton = DATOS.getActionCommand();
			if (Boton.compareTo("Limpiar") == 0)
			{
				JTF1.setText(""); JTF2.setText(""); Resp.setText(""); 
			}
			else
			{
				int Dato1 = Integer.parseInt(JTF1.getText());
				int Dato2 = Integer.parseInt(JTF2.getText());
				int Respuesta = Dato1 + Dato2;
				Resp.setText("" + Respuesta);
			}
		}
	}	// FIN DE LA CLASE EVENTO
}		// FIN DE LA CLASE PRINCIPAL
