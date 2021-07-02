# Graficacion-Proyecto
  #include <stdio.h>
  #include <conio.h>
  #include <graphics.h>
  #include <math.h>
  #include <dos.h>

  int main() {
      
        int gdriver = DETECT, gmode;
        float x1, y1, x2, y2;
        float err, x, y, dx, dy, dp, xEnd;
        float twody, twodxdy;
 
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
               
                printf("Graphics Error: %s\n",
                                grapherrormsg(err));
                return 0;
        }

  
        dx = x2 - x1;
        dy = y2 - y1;

        twody = 2 * dy;
        twodxdy = 2 * (dy - dx);

        dp = twody - dx;

        if (x1 > x2) {
                x = x2;
                y = y2;
                xEnd = x1;
        } else {
                x = x1;
                y = y1;
                xEnd = x2;
        }

        putpixel(x, y, WHITE);

      
        while (x < xEnd) {
                x = x + 1;
                if (dp < 0) {
                        dp = dp + twody;
                } else {
                        y = y + 1;
                        dp = dp + twodxdy;
                }

                putpixel(x, y, WHITE);

                delay(50);
        }

        getch();

        closegraph();

        return 0;
  }
