#include <iostream>
using namespace std;
// Abstract base class
class Shape {
public:
    virtual double calculateArea() const = 0; // Pure virtual function
    virtual ~Shape() {}// Virtual destructor 
};
class Circle : public Shape {
private:
    double radius;
public:
    Circle(double r) : radius(r) {}
    // Implementation of the pure virtual function
    double calculateArea() const override {
        return 3.14159 * radius * radius;
    }
};
class Rectangle : public Shape {
private:
    double length;
    double width;
public:
    Rectangle(double l, double w) : length(l), width(w) {}
    double calculateArea() const override {
        return length * width;
    }
};

int main() {
    Circle circle(5.0);
    Rectangle rectangle(4.0, 6.0);
    Shape* shape1 = &circle;
    Shape* shape2 = &rectangle;
    cout << "Area of the circle: " << shape1->calculateArea() << endl;
    cout << "Area of the rectangle: " << shape2->calculateArea() << endl;
    return 0;
}
