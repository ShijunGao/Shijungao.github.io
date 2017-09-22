>小作业之 Verify the Discrete Gauss-Bonnet theorem

*half edge*
``` C++
//遍历halfedge
//只能将先马后看
for (VertexInHalfedgeIterator vhiter(this, pV); !vhiter.end(); ++vhiter) {
	H * pH = *vhiter;
	//you can do something to the incoming halfedges with CCW
	//...
	CHalfEdge * Next = pH->he_next();
	CHalfEdge * UnderNext = pH->he_next()->he_next();
	CPoint nextV = Next->target()->point();
	CPoint UnderNextV = UnderNext->target()->point();
	CPoint currentV = pV->point();
	double a = pow((currentV[0] - nextV[0]), 2);
	double b = pow((currentV[1] - nextV[1]), 2);
	double c = pow((currentV[2] - nextV[2]), 2);
	double m = sqrt(a + b + c);
	double aa = pow((currentV[0] - UnderNextV[0]), 2);
	double bb = pow((currentV[1] - UnderNextV[1]), 2);
	double cc = pow((currentV[2] - UnderNextV[2]), 2);
	double n = sqrt(aa + bb + cc);
	double aaa = pow((nextV[0] - UnderNextV[0]), 2);
	double bbb = pow((nextV[1] - UnderNextV[1]), 2);
	double ccc = pow((nextV[2] - UnderNextV[2]), 2);
	double p = sqrt(aaa + bbb + ccc);
	temp += acos((m * m + n * n - p * p) / (2 * m*n));
}
```
