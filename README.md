# KT-1
class Point {
    constructor(public x: number, public y: number) {}
}

class Triangle {
    point1: Point;
    point2: Point;
    point3: Point;

    constructor(point1?: Point, point2?: Point, point3?: Point, x1?: number, y1?: number, x2?: number, y2?: number, x3?: number, y3?: number) {
        if (point1 && point2 && point3) {
            this.point1 = point1;
            this.point2 = point2;
            this.point3 = point3;
        } else if (x1 !== undefined && y1 !== undefined && x2 !== undefined && y2 !== undefined && x3 !== undefined && y3 !== undefined) {
            this.point1 = new Point(x1, y1);
            this.point2 = new Point(x2, y2);
            this.point3 = new Point(x3, y3);
        } else {
            throw new Error("Invalid arguments provided");
        }
    }
}

const triangle1 = new Triangle(new Point(0, 0), new Point(1, 0), new Point(0, 1));
const triangle2 = new Triangle(undefined, undefined, undefined, 0, 0, 1, 0, 0, 1);

console.log(triangle1);
console.log(triangle2);
