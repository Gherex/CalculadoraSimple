import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import javax.swing.border.*;

public class Calculadora implements ActionListener {

  private JFrame pantalla = new JFrame();
  private JButton b0,b1,b2,b3,b4,b5,b6,b7,b8,b9,bSuma,bResta,bDiv,bMulti,bIgual,bPunto,bBorrar,bReset;
  private JPanel display = new JPanel();
  private JLabel labelRes, labelEmail;
  private String resultado = "";
  private float prevCalc = 0f;
  private Boolean noTienePunto = true;
  private String operacion = "";
  private Boolean presionoIgual = false;
  private String valorAnterior = "";

  public Calculadora() {
    
    pantalla.setLayout(null);
    pantalla.setSize(330,500);
    pantalla.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    pantalla.setTitle("Calculadora básica");
    pantalla.setLocationRelativeTo(null);
    pantalla.setResizable(false);
    
    labelRes = new JLabel(resultado);
    labelRes.setBounds(10,20,295,40);
    labelRes.setFont(new Font("Arial", Font.PLAIN, 24));
    labelRes.setHorizontalAlignment(SwingConstants.RIGHT);
    labelRes.setBorder(new EmptyBorder(10, 10, 10, 20));
    labelRes.setBackground(new Color(210,210,210));
    labelRes.setOpaque(true);
    pantalla.add(labelRes);

    bDiv = new JButton("/");
    bDiv.setBounds(20, 70, 60, 60);
    bDiv.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bDiv);
    bDiv.addActionListener(this);

    bMulti = new JButton("*");
    bMulti.setBounds(90, 70, 60, 60);
    bMulti.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bMulti);
    bMulti.addActionListener(this);

    bReset = new JButton("Reset");
    bReset.setBounds(160, 70, 60, 60);
    bReset.setFont(new Font("Arial", Font.BOLD, 9));
    pantalla.add(bReset);
    bReset.addActionListener(this);

    bBorrar = new JButton("Borrar");
    bBorrar.setBounds(230, 70, 60, 60);
    bBorrar.setFont(new Font("Arial", Font.BOLD, 8));
    pantalla.add(bBorrar);
    bBorrar.addActionListener(this);

    b7 = new JButton("7");
    b7.setBounds(20, 140, 60, 60);
    b7.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b7);
    b7.addActionListener(this);

    b8 = new JButton("8");
    b8.setBounds(90, 140, 60, 60);
    b8.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b8);
    b8.addActionListener(this);

    b9 = new JButton("9");
    b9.setBounds(160, 140, 60, 60);
    b9.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b9);
    b9.addActionListener(this);

    bResta = new JButton("-");
    bResta.setBounds(230, 140, 60, 60);
    bResta.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bResta);
    bResta.addActionListener(this);

    b4 = new JButton("4");
    b4.setBounds(20, 210, 60, 60);
    b4.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b4);
    b4.addActionListener(this);

    b5 = new JButton("5");
    b5.setBounds(90, 210, 60, 60);
    b5.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b5);
    b5.addActionListener(this);

    b6 = new JButton("6");
    b6.setBounds(160, 210, 60, 60);
    b6.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b6);
    b6.addActionListener(this);

    bSuma = new JButton("+");
    bSuma.setBounds(230, 210, 60, 60);
    bSuma.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bSuma);
    bSuma.addActionListener(this);

    b1 = new JButton("1");
    b1.setBounds(20, 280, 60, 60);
    b1.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b1);
    b1.addActionListener(this);

    b2 = new JButton("2");
    b2.setBounds(90, 280, 60, 60);
    b2.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b2);
    b2.addActionListener(this);

    b3 = new JButton("3");
    b3.setBounds(160, 280, 60, 60);
    b3.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b3);
    b3.addActionListener(this);

    bIgual = new JButton("=");
    bIgual.setBounds(230, 280, 60, 130);
    bIgual.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bIgual);
    bIgual.addActionListener(this);

    b0 = new JButton("0");
    b0.setBounds(20, 350, 130, 60);
    b0.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(b0);
    b0.addActionListener(this);

    bPunto = new JButton(".");
    bPunto.setBounds(160, 350, 60, 60);
    bPunto.setFont(new Font("Arial", Font.BOLD, 24));
    pantalla.add(bPunto);
    bPunto.addActionListener(this);

    labelEmail = new JLabel("germilagger@gmail.com");
    labelEmail.setBounds(0,420,330,20);
    labelEmail.setFont(new Font("Arial", Font.PLAIN, 14));
    labelEmail.setHorizontalAlignment(SwingConstants.CENTER);
    pantalla.add(labelEmail);

    pantalla.setVisible(true);
  }

  @Override
  public void actionPerformed(ActionEvent e) {
    if (e.getSource() == b0 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "0";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b1 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "1";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b2 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "2";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b3 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "3";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b4 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "4";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b5 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "5";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b6 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "6";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b7 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "7";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b8 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "8";
      labelRes.setText(resultado);
    }
    if (e.getSource() == b9 && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + "9";
      labelRes.setText(resultado);
    }
    if (noTienePunto && e.getSource() == bPunto && !presionoIgual) {
      valorAnterior = resultado;
      resultado = resultado + ".";
      labelRes.setText(resultado);
      noTienePunto = false;
    }
    if (e.getSource() == bReset) {
      resultado = "";
      prevCalc = 0f;
      operacion = "";
      labelRes.setText("");
      presionoIgual = false;
      valorAnterior = "";
    }
    if (e.getSource() == bBorrar && valorAnterior != "") {
      resultado = valorAnterior;
      labelRes.setText(resultado);
      valorAnterior="";
    }
    if (resultado != "" && prevCalc != 0f && e.getSource() == bIgual && operacion != "" && Float.parseFloat(resultado) != 0f) {
      presionoIgual = true;
      if (operacion == "+") prevCalc = prevCalc + Float.parseFloat(resultado);
      if (operacion == "-") prevCalc = prevCalc - Float.parseFloat(resultado);
      if (operacion == "*") prevCalc = prevCalc * Float.parseFloat(resultado);
      if (operacion == "/") prevCalc = prevCalc / Float.parseFloat(resultado);
      labelRes.setText(String.valueOf(prevCalc));
      resultado="";
      noTienePunto=true;
    }


    if (!presionoIgual && resultado != "" && prevCalc == 0f && e.getSource() == bSuma) {
      noTienePunto = true;
      prevCalc = Float.parseFloat(resultado);
      resultado = "";
      operacion = "+";
      labelRes.setText("+");
    }
    if (!presionoIgual && resultado != "" && prevCalc == 0f && e.getSource() == bResta) {
      noTienePunto = true;
      prevCalc = Float.parseFloat(resultado);
      resultado = "";
      operacion = "-";
      labelRes.setText("-");
    }
    if (!presionoIgual && resultado != "" && prevCalc == 0f && e.getSource() == bMulti) {
      noTienePunto = true;
      prevCalc = Float.parseFloat(resultado);
      resultado = "";
      operacion = "*";
      labelRes.setText("*");
    }
    if (!presionoIgual && resultado != "" && prevCalc == 0f && e.getSource() == bDiv) {
      noTienePunto = true;
      prevCalc = Float.parseFloat(resultado);
      resultado = "";
      operacion = "/";
      labelRes.setText("/");
    }

    if (presionoIgual && prevCalc != 0f && e.getSource() == bSuma) {
      noTienePunto = true;
      presionoIgual = false;
      operacion = "+";
      labelRes.setText("+");
    }
    if (presionoIgual && prevCalc != 0f && e.getSource() == bResta) {
      noTienePunto = true;
      presionoIgual = false;
      operacion = "-";
      labelRes.setText("-");
    }
    if (presionoIgual && prevCalc != 0f && e.getSource() == bMulti) {
      noTienePunto = true;
      presionoIgual = false;
      operacion = "*";
      labelRes.setText("*");
    }
    if (presionoIgual && prevCalc != 0f && e.getSource() == bDiv) {
      noTienePunto = true;
      presionoIgual = false;
      operacion = "/";
      labelRes.setText("/");
    }

    if (resultado != "" && prevCalc != 0f && e.getSource() == bSuma) {
      noTienePunto = true;
      prevCalc = prevCalc + Float.parseFloat(resultado);
      resultado = "";
      labelRes.setText(String.valueOf(prevCalc));
    }
    if (resultado != "" && prevCalc != 0f && e.getSource() == bResta) {
      noTienePunto = true;
      prevCalc = prevCalc - Float.parseFloat(resultado);
      resultado = "";
      labelRes.setText(String.valueOf(prevCalc));
    }
    if (resultado != "" && prevCalc != 0f && e.getSource() == bMulti) {
      noTienePunto = true;
      prevCalc = prevCalc * Float.parseFloat(resultado);
      resultado = "";
      labelRes.setText(String.valueOf(prevCalc));
    }
    if (resultado != "" && prevCalc != 0f && e.getSource() == bDiv && Float.parseFloat(resultado) != 0f ) {
      noTienePunto = true;
      prevCalc = prevCalc / Float.parseFloat(resultado);
      resultado = "";
      labelRes.setText(String.valueOf(prevCalc));
    }


  }

  
  public static void main(String[] args) {
    new Calculadora();
  }
}