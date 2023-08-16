#include <glut.h>
#include <iostream>
using namespace std;

int x[4], y[4];
int choice;
float h;

void init() {
    glClearColor(0.0, 0.0, 0.0, 0.0);
}

void rectangleX(int& x1, int& y1) {
    x1 = x1 + y1 * h;
    y1 = y1;
}

void rectangleY(int& x1, int& y1) {
    x1 = x1;
    y1 = y1 + x1 * h;
}
void drawFinal() {
    glClear(GL_COLOR_BUFFER_BIT);
    glColor3f(1.0, 1.0, 1.0);
    glPointSize(2.0);

    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-500, 500, -500, 500);

    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();

    glBegin(GL_LINES);

    glVertex2i(x[1], y[1]);
    glVertex2i(x[2], y[2]);

    glVertex2i(x[2], y[2]);
    glVertex2i(x[3], y[3]);

    glVertex2i(x[3], y[3]);
    glVertex2i(x[4], y[4]);

    glVertex2i(x[4], y[4]);
    glVertex2i(x[1], y[1]);

    glEnd();
    glFlush();

}
void display() {
    glClear(GL_COLOR_BUFFER_BIT);
    glColor3f(1.0, 1.0, 1.0);
    glPointSize(2.0);

    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-500, 500, -500, 500);

    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();

    glBegin(GL_LINES);
    // Draw the original rectangle
    glVertex2i(x[1], y[1]);
    glVertex2i(x[2], y[2]);

    glVertex2i(x[2], y[2]);
    glVertex2i(x[3], y[3]);

    glVertex2i(x[3], y[3]);
    glVertex2i(x[4], y[4]);

    glVertex2i(x[4], y[4]);
    glVertex2i(x[1], y[1]);

    // Draw the transformed rectangle based on the user's choice
    if (choice == 1) {
        for (int i = 1; i <=4; i++) {
            rectangleX(x[i], y[i]);
        }
        drawFinal();
    
    }
    else if (choice == 2) {
        for (int i = 1; i <= 4; i++) {
            rectangleY(x[i], y[i]);
            drawFinal();
            }
    }

    glEnd();
    glFlush();
}

int main(int argc, char** argv) {
    cout << "Enter the four points of the rectangle in clockwise order starting from the top left corner.\n";
    for (int i = 1; i <= 4; i++) {
        cout << "Enter the " << i << " point of rectangle: ";
        cin >> x[i] >> y[i];
    }
    cout << "Enter 1 for X axis shearing and 2 for Y-axis: ";
    cin >> choice;
    cout << "Enter the value of h: ";
    cin >> h;

    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
    glutInitWindowSize(500, 500);
    glutCreateWindow("Shearing transformation on a rectangle");
    init();
    glutDisplayFunc(display);
    glutMainLoop();
    return 0;
}
