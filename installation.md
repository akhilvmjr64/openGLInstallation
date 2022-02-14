# Use the following command on linux to install the OpenGL
### Ubuntu:
```
sudo apt-get install -y libglu1-mesa-dev freeglut3-dev mesa-common-dev
```

# Checking if installation was successful

And create a C program with the following code to check if OpenGL is successfully installed

```c
#include <GL/glut.h>

void displayMe(void)
{
    glClear(GL_COLOR_BUFFER_BIT);
    glBegin(GL_POLYGON);
    glVertex3f(0.5, 0.25, 0.5);
    glVertex3f(0.5, 0.5, 0.25);
    glVertex3f(0.25, 0.5, 0.5);
    glEnd();
    glFlush();
}

int main(int argc, char** argv)
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_SINGLE);
    glutInitWindowSize(400, 300);
    glutInitWindowPosition(100, 100);
    glutCreateWindow("Hello world!");
    glutDisplayFunc(displayMe);
    glutMainLoop();
    return 0;
}
```

Compile the code using the following command
```sh
gcc <program_name> -o <output_name> -lglut -lGLU -lGL
```
