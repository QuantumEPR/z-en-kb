---
title: Java
date: 2017-11-16T19:12:21-07:00
showDate: true
publishDate: 2017-11-16
---
## Let's have a cup of coffee, shall we?

Good Programs are elegant, and I genuinely adore all the creativity and productivity it encapsulates. It's simple as the code we write, yet complicated as mind we use. The following is a piece of code where I try to do an animation without using a `sleep` call, and I was able to do it by using the natural lag off of computers in physical world. (Basically cramming up a ton of calculations so that the process is elongated.) 

```java
public class MyTriangle {
    public static void main(String[] args) {
        DrawingPanel drawingPanel = new DrawingPanel(1000, 1000);
        drawingPanel.setBackground(Color.WHITE);
        Graphics pen = drawingPanel.getGraphics();
        rotation1(pen, 100,1,1);
        rotation1(pen, 50,1,-1);
        rotation1(pen, 25,1,1);
        rotation1(pen, 13,1,-1);
    }

    public static void rotation1(Graphics g, int r, int angle, int direction) {
        for (double t = Math.PI / angle; t < 2 * Math.PI / 3 + Math.PI / angle; t = t + 0.00001) { //for loop that repeats to create triangles
            double x1 = r * Math.cos(t) + 500;
            double x2 = r * Math.cos(t + 2 * Math.PI / 3) + 500;
            double x3 = r * Math.cos(t + 4 * Math.PI / 3) + 500;
            double y1 = -1 * r * Math.sin(t) * direction + 500;
            double y2 = -1 * r * Math.sin(t + 2 * Math.PI / 3) * direction + 500;
            double y3 = -1 * r * Math.sin(t + 4 * Math.PI / 3) * direction + 500;

            //connects three points of the triangle from calculations above
            g.drawLine((int) x1, (int) y1, (int) x2, (int) y2);
            g.drawLine((int) x2, (int) y2, (int) x3, (int) y3);
            g.drawLine((int) x3, (int) y3, (int) x1, (int) y1);
        }
    }
}
```

My belief in computing is that it can empower other fields of studies. The nature of algorithmic thinking, where we train our minds to treat problems accordingly, will bring us to and beyond an era of information.

---
[[Badminton]]
[[Designing Future]]
[[The Foothill]]
[[Memoir...Reflected]]