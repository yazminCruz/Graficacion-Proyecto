# Graficacion-Proyecto
#include <stdio.h>
  #include <conio.h>
  #include <graphics.h>
  #include <math.h>
  #include <dos.h>

  int main() {
    
        int gdriver = DETECT, gmode, err;
        float i, x1, y1, x2, y2, dx, dy, steps;
        float x, y, xincr, yincr;

	printf("INGRESAR LAS COORDENADA X1 ");
  		printf("\n");
         
        scanf("%f",&x1);
        
        printf("INGRESAR LAS COORDENADA y1 ");
        printf("\n");
        
        scanf("%f",&y1);
        
        printf("INGRESAR LAS COORDENADA X2 ");
        printf("\n");
        
        scanf("%f",&x2);
        
        printf("INGRESAR LAS COORDENADA y2 ");
        printf("\n");
        
        scanf("%f",&y2);
        
      
        initgraph(&gdriver, &gmode, "C:/TURBOC3/BGI");

        err = graphresult();

        if (err != grOk) {
               
                printf("Graphic Error: %s\n",
                                grapherrormsg(err));
                getch();
                return 0;
        }

        
        dx = x2 - x1;
        dy = y2 - y1;

        x = x1, y = y1;

        steps = abs(dx) > abs(dy) ? dx : dy;

        xincr = (1.0 * dx) / steps;
        yincr = (1.0 * dy) / steps;

        putpixel((int) x, (int) y, WHITE);

        for (i = 0; i < steps; i++) {
                x = x + xincr;
                y = y + yincr;

                putpixel((int) x, (int) y, WHITE);

                delay(50);
        }

        closegraph();
        return 0;
  }
