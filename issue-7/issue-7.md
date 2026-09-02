# test linux scooby report without numpy
Scooby report:

```code
--------------------------------------------------------------------------------
  Date: Tue Jul 14 15:08:33 2026 UTC

                OS : Linux (Debian GNU/Linux 13)
            CPU(s) : 2
           Machine : x86_64
      Architecture : 64bit
       Environment : Python

  Python 3.12.13 | packaged by conda-forge | (main, Jul 14 2026, 04:46:18) [GCC 14.2.0]

           pygimli : 1.6.0
            pgcore : 1.6.0
        matplotlib : Module not found
--------------------------------------------------------------------------------
```

Hi!

I am trying to use pygimly to perform a gravimetric inversion. The
gravimetric profile i want to invert has a length of about 35
kilometers, but I only need the mesh to be a few hundred meters deep,
and this has brought me issues generating an adequate mesh. Here you can
see my code, I also attach file with the boundaries of the mesh, and an
image showing the mesh I have been able to generate so far. I would
really appreciate if someone has any recomendation on how I can improve
this.

```code
import numpy as np
import pygimli as pg
import pygimli.meshtools as mt

mesh_bounds = np.loadtxt(r'./Files/mesh_bounds.txt', delimiter=',')
mesh_bounds = mesh_bounds.tolist()

topo = mt.createPolygon(mesh_bounds, isClosed=True, marker=1, area=1)
mesh = mt.createMesh(topo, quality=32)
ax, _ = pg.show(mesh)
ax.set_aspect(30)
```

Thank you very much!

![Image](https://github.com/user-attachments/assets/30164f96-6acd-4a0f-ac28-c862b57e575a)

[mesh_bounds.txt](https://github.com/user-attachments/files/20647875/mesh_bounds.txt)