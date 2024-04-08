# PROYECTOJAVA
Proyecto que implenta 3 valores para dar o saber si es un triangulo recto, isosceles, escaleno

package com.mycompany.tringulo;

import javax.swing.JOptionPane;

/**
 *
 * @author ACER
 */
public class Tringulo {
    
 public static void main(String[] args) {
     
        double x1 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada x del primer vértice:"));
        double y1 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada y del primer vértice:"));
        double x2 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada x del segundo vértice:"));
        double y2 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada y del segundo vértice:"));
        double x3 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada x del tercer vértice:"));
        double y3 = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la coordenada y del tercer vértice:"));
        

        double lado1 = Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
        double lado2 = Math.sqrt(Math.pow(x3 - x2, 2) + Math.pow(y3 - y2, 2));
        double lado3 = Math.sqrt(Math.pow(x1 - x3, 2) + Math.pow(y1 - y3, 2));
 

        double perimetro = lado1 + lado2 + lado3;
        double semiperimetro = perimetro / 2;
       
        double area = Math.sqrt(semiperimetro * (semiperimetro - lado1) * (semiperimetro - lado2) * (semiperimetro - lado3));

        double angulo1 = Math.acos((lado2 * lado2 + lado3 * lado3 - lado1 * lado1) / (2 * lado2 * lado3));
        double angulo2 = Math.acos((lado1 * lado1 + lado3 * lado3 - lado2 * lado2) / (2 * lado1 * lado3));
        double angulo3 = Math.acos((lado1 * lado1 + lado2 * lado2 - lado3 * lado3) / (2 * lado1 * lado2));

        angulo1 = Math.toDegrees(angulo1);
        angulo2 = Math.toDegrees(angulo2);
        angulo3 = Math.toDegrees(angulo3);

        
        String tipoTriangulo;
        if (lado1 == lado2 && lado2 == lado3) {
            tipoTriangulo = "Equilátero";
        } else if (lado1 == lado2 || lado1 == lado3 || lado2 == lado3) {
            tipoTriangulo = "Isósceles";
        } else {
            tipoTriangulo = "Escaleno";
        }

        JOptionPane.showMessageDialog(null, "Tipo de triángulo: " + tipoTriangulo + "\nPerímetro: "
                + perimetro + "\nÁrea: " + area + "\nÁngulo 1: " + angulo1 + " grados\nÁngulo 2: " + angulo2 +
                " grados\nÁngulo 3: " + angulo3 + " grados");
    }
}
