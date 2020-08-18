---
layout: post
title:  "Mid Point Circle drawing Algorithm In OpenGL C++"
date:   2016-04-21 14:41:47 +0530
categories: [unix, macOS, openGL]
tags: [unix, macOS, openGL]
---

```c++
#include<GLUT/glut.h>
#include<stdio.h>
GLint xc,yc,r,sizes=1000;
void myInit(void)
{
    glClearColor(0.0,1.0,1.0,0.0);
    glColor3f(1.0f,0.0f,0.0f);
    glPointSize(3.0);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    //gluOrtho2D(0.0,640.0,0.0,480.0);
    glOrtho(-sizes/2,sizes/2,-sizes/2,sizes/2,-1,1);
}
void readInput()
{

    printf("Enter xc, yc, radius(resp): ");
    scanf("%i %i %i",&xc,&yc,&r);

}
void setPixel(GLint xcoordinate, GLint ycoordinate)
{
    glBegin(GL_POINTS);
    glVertex2i(xcoordinate,ycoordinate);
    glEnd();
    glFlush();
}
void draw_axis()
{
    GLint i=(-sizes)/2;
    for(;i<(sizes/2);i++)
    {
        setPixel(i,0);
        setPixel(0,i);
    }

}
void draw_in_each_oct(GLint xk,GLint yk, GLint xc,GLint yc)
{
    setPixel(xc+xk,yc+yk);
    setPixel(xc+yk,yc+xk);
    setPixel(xc-yk,yc+xk);
    setPixel(xc-xk,yc+yk);
    setPixel(xc-xk,yc-yk);
    setPixel(xc-yk,yc-xk);
    setPixel(xc+yk,yc-xk);
    setPixel(xc+xk,yc-yk);
}

void midPtCircle(GLint xc,GLint yc,GLint r)
{
    GLint pk,xk,yk;
    pk=1-r;
    xk=0;
    yk=r;
    draw_in_each_oct(xk,yk,xc,yc);
    while(xk<=yk)
    {
        if(pk<0)
        {
            xk=xk+1;
            pk=pk+(2*xk)+1;
        }
        else
        {
            xk=xk+1;
            yk=yk-1;
            pk=pk+(2*xk)+1-(2*yk);
        }
        draw_in_each_oct(xk,yk,xc,yc);
    }

}


void Display(void)
{
    glClear(GL_COLOR_BUFFER_BIT);
    draw_axis();
    midPtCircle(xc,yc,r);
}

int main(int argc,char *argv[])
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
    glutInitWindowSize(600,600);
    glutInitWindowPosition(50,50);
    glutCreateWindow("Mid Point Circle");
    readInput();
    glutDisplayFunc(Display);
    myInit();
    glutMainLoop();
    return 0;
}
```
