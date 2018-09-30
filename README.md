# prakitika3ikbo16-17-Boldyrev-Grigoriy
# Задание 1
# Shape
public abstract class Shape
{
    protected String color;
    protected boolean filled;

    public String getColor(){
        this.color=color;
        return color;
    }

    public boolean getFilled(){
        this.filled=filled;
        return filled;
    }

    public String setColor(){
        this.color=color;
        return color;
    }
    public boolean isFilled(){
        this.filled=filled;
        return filled;
    }

    public boolean setFilled(){
        this.filled=filled;
        return filled;
    }


    public abstract double getArea();
    public abstract double getPerimeter();
    public  abstract  String toString();
}

# Circle
import java.math.*;

public class Circle extends Shape {
    protected double radius;
    protected String color;
    protected boolean filled;
    public Circle(){}
    public Circle(double radius, String color, boolean filled){
        this.radius=radius;
        this.color =color;
    }
    public double getRadius(){
        this.radius = radius;
        return radius;
    }

    public void setRadius(double radius){
        this.radius = radius;
    }

    public double getArea(){
        return Math.PI*radius*radius;
    }

    public double getPerimeter(){
        return 2*Math.PI*radius;
    }


    public String toString() {
        return "Shape: circle, radius: "+this.radius+", color"+this.color;
    }
}
# Rectangle
public class Rectangle extends Shape {
    protected double width;
    protected double length;

    public Rectangle() {
    }

    Rectangle(double with, double length) {

    }

    public Rectangle(double with, double length, String color, boolean filled) {
        this.width = 3;
        this.length = 5;
        this.color = "white";
        this.filled = true;
    }

    public double getWidth() {
        this.width = width;
        return width;
    }

    public double getLength() {
        this.length = length;
        return length;
    }

    public void setWidth(double width) {
        this.width = width;
    }

    public void setLength(double length) {
        this.length = length;
    }

    public double getArea() {
        double a = width * length;
        return a;
    }

    public double getPerimeter() {
        double p = (width + length) * 2;
        return p;
    }


    public String toString() {
        return "Shape: rectangle, width: " + this.width + ", length: " + this.length;
    }
}

# Square
public class Square extends Rectangle {
        protected double side;
        public  Square(){
            this.side=side;
        }

        public double Square(double side){
            this.side=side;
            return side;
        }

        Square(double side, String color, boolean filled){
            this.side=12;
            this.color="white";
            this.filled=true;

        }

        public double getSide(){
            this.side=side;
            return side;
        }

        public void setSide(double side){
            this.side=side;

        }

        public void setWidth(double side){
            this.side= width;
        }

        public void setLength(double side){
            this.side=length;
        }


        public String toString() {
            return "Shape: square, side: "+this.side+", color "+this.color;
        }
    }
    
# Main
    public class Main {
    public static main()
    Shape s1 = new Circle(5.5, "RED", false);  // Upcast Circle to Shape
System.out.println(s1);                    // which version?
System.out.println(s1.getArea());          // which version?
    System.out.println(s1.getPerimeter());     // which version?
    System.out.println(s1.getColor());
    System.out.println(s1.isFilled());
    System.out.println(s1.getRadius());
    Circle c1 = (Circle)s1;                   // Downcast back to Circle
     System.out.println(c1);
    System.out.println(c1.getArea());
            System.out.println(c1.getPerimeter());
            System.out.println(c1.getColor());
            System.out.println(c1.isFilled());
            System.out.println(c1.getRadius());
    Shape s2 = new Shape();
    Shape s3 = new Rectangle(1.0, 2.0, "RED", false);   // Upcast
System.out.println(s3);
System.out.println(s3.getArea());
System.out.println(s3.getPerimeter());
System.out.println(s3.getColor());
System.out.println(s3.getLength());
    Rectangle r1 = (Rectangle)s3;   // downcast
    System.out.println(r1);
    System.out.println(r1.getArea());
    System.out.println(r1.getColor());
    System.out.println(r1.getLength());
    Shape s4 = new Square(6.6);     // Upcast
    System.out.println(s4);
    System.out.println(s4.getArea());
    System.out.println(s4.getColor());
    System.out.println(s4.getSide());
    // Take note that we downcast Shape s4 to Rectangle,
    //  which is a superclass of Square, instead of Square
    Rectangle r2 = (Rectangle)s4;
    System.out.println(r2);
    System.out.println(r2.getArea());
    System.out.println(r2.getColor());
    System.out.println(r2.getSide());
    System.out.println(r2.getLength());
    // Downcast Rectangle r2 to Square
    Square sq1 = (Square)r2;
    System.out.println(sq1);
    System.out.println(sq1.getArea());
    System.out.println(sq1.getColor());
    System.out.println(sq1.getSide());
    System.out.println(sq1.getLength());
    //не определенны методы в классе фигуры
}


# Задание 2
# Movable
public interface Movable {
    public void moveUp();
    public void moveDown();
    public void moveLeft();
    public void moveRight();
}

# MovableCircle

public class MovableCircle extends MovablePoint implements Movable  {
    public int x;
    public int y;
    public int xSpeed;
    public int ySpeed;
    private int radius;
    private MovablePoint center;
    MovableCircle(int x, int y, int xSpeed, int ySpeed, int radius) {
        this.x = x;
        this.y = y;
        this.xSpeed = xSpeed;
        this.ySpeed = ySpeed;
        this.radius = radius;
    }
    @Override
    public String toString() {
        return "x: " + x + ", y: " + y + ", xSpeed: " + xSpeed + ", ySpeed: " + ySpeed + ", radius: " + radius + "\n";
    }
    public void moveUp() {
        y+= 1;
    }
    public void moveDown() {
        y-= 1;
    }
    public void moveLeft() {
        x-= 1;
    }
    public void moveRight() {
        x+= 1;
    }
}

# MovablePoint

public class MovablePoint implements Movable {
    public int x;
    public int y;
    public int xSpeed;
    public int ySpeed;
    MovablePoint() {
        x = 1;
        y = 1;
        xSpeed = 1;
        ySpeed = 1;
    }
    MovablePoint(int x, int y, int xSpeed, int ySpeed) {
        this.x = x;
        this.y = y;
        this.xSpeed = xSpeed;
        this.ySpeed = ySpeed;
    }
    @Override
    public String toString() {
        return "x: " + x + ", y: " + y + ", xSpeed: " + xSpeed + ", ySpeed: " + ySpeed + "\n";
    }
    public void moveUp() {
        y+= 1;
    }
    public void moveDown() {
        y-= 1;
    }
    public void moveLeft() {
        x-= 1;
    }
    public void moveRight() {
        x+= 1;
    }
}

# MovableRectangle

public class MovableRectangle extends MovablePoint implements Movable  {
    public int x;
    public int y;
    public int xSpeed;
    public int ySpeed;
    private MovablePoint topLeft;
    private MovablePoint bottomRight;
    MovableRectangle(int x, int y, int xSpeed, int ySpeed) {
        x = 1;
        y = 1;
        xSpeed = 1;
        ySpeed = 1;
    }
    @Override
    public String toString() {
        return "x: " + x + ", y: " + y + ", xSpeed: " + xSpeed + ", ySpeed: " + ySpeed + "\n";
    }
    public void moveUp() {
        y+= 1;
    }
    public void moveDown() {
        y-= 1;
    }
    public void moveLeft() {
        x-= 1;
    }
    public void moveRight() {
        x+= 1;
    }
}





# Ошибки в первом задании

System.out.println(s1.getRadius()); // Строка 9, у фигуры фигура нет метода получить радиус
Shape s2 = new Shape(); // Класс Shape является астрактным, нельзя объявить
System.out.println(s3.getLength()); // В классе Sharp нет метода getLength
System.out.println(s4.getSide()); // В классе Sharp нет метода getSide
System.out.println(r2.getSide()); // В классе Rectangle нет метода getSize
