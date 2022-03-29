# assignment 04
Terdapat kode Python berikut

```python
"""
Matplotlib Animation Example

author: Jake Vanderplas
email: vanderplas@astro.washington.edu
website: http://jakevdp.github.com
license: BSD
Please feel free to use and modify this, but keep the above information. Thanks!
"""

import numpy as np
from matplotlib import pyplot as plt
from matplotlib import animation

# First set up the figure, the axis, and the plot element we want to animate
fig = plt.figure()
ax = plt.axes(xlim=(0, 2), ylim=(-2, 2))
line, = ax.plot([], [], lw=2)

# initialization function: plot the background of each frame
def init():
    line.set_data([], [])
    return line,

# animation function.  This is called sequentially
def animate(i):
    x = np.linspace(0, 2, 1000)
		
		# ---- equation of y ----
		
		# -----------------------
		
    line.set_data(x, y)
    return line,

# call the animator.  blit=True means only re-draw the parts that have changed.
anim = animation.FuncAnimation(fig, animate, init_func=init,
                               frames=200, interval=20, blit=True)

# save the animation as an mp4.  This requires ffmpeg or mencoder to be
# installed.  The extra_args ensure that the x264 codec is used, so that
# the video can be embedded in html5.  You may need to adjust this for
# your system: for more information, see
# http://matplotlib.sourceforge.net/api/animation_api.html
#anim.save('basic_animation.mp4', fps=30, extra_args=['-vcodec', 'libx264'])

#plt.show()


# lines above this line is the original code from Jake Vanderplas
# url https://jakevdp.github.io/downloads/code/basic_animation.py

# modification from Sparisoma Viridi 2022-03-29
option = 1

if option == 0:
	writergif = animation.PillowWriter(fps=30)
	anim.save('basic_animation.gif', writer=writergif)
# anim.save('basic_animation.mp4', fps=30, extra_args=['-vcodec', 'libx264'])
else:
	plt.show()


```
yang dapat diperoleh di <https://jakevdp.github.io/downloads/code/basic_animation.py>.

## question 1
Baca penjelasan mengenai kode di atas pada <https://dudung.github.io/bugx/0026/> atau pada pertemuan kuliah terkait.

### answer 1
Apakah penjelasan kode dia atas sudah dibaca atau hadir pada kuliah?
```
Sudah
```

## question 2
Modifikasi program yang diberikan sehingga dapat menggambarkan gelombang yang merambat ke kanan dengan panjang gelombang &lambda; = 2 m dan periode T = 2 s. Perolehlah pula berkas gif hasilnya.

### answer 2
Potongan kode yang perlu disisipkan adalah
```
y = np.sin(2*np.pi*(0.5*x - 0.5*i))
```
dan hasil berkas gifnya adalah \
![![gelombang ke kanan](https://user-images.githubusercontent.com/97928815/160529438-e2e5de82-5e0d-45ff-ad44-6ebcb3e2cf6d.png)
]()


## question 3
Modifikasi program yang diberikan sehingga dapat menggambarkan gelombang yang merambat ke kiri dengan panjang gelombang &lambda; = 2 m dan periode T = 2 s. Perolehlah pula berkas gif hasilnya.

### answer 3
Potongan kode yang perlu disisipkan adalah
```
y = np.sin(2*np.pi*(0.5*x - 0.5*i))
```
dan hasil berkas gifnya adalah \
![![Gelombang ke kiri](https://user-images.githubusercontent.com/97928815/160537326-8c0cca92-eb09-4f87-a8b0-45eeef090e4a.png)
]()


## question 4
Modifikasi program yang diberikan sehingga dapat menggambarkan gelombang stasioner yang tidak merambat dengan panjang gelombang &lambda; = 2 m dan periode T = 2 s. Perolehlah pula berkas gif hasilnya.

### answer 4
Potongan kode yang perlu disisipkan adalah
```
y = np.sin(2*np.pi*0.5*x)*np.cos(2*np.pi*0.125*i)
dan periode yang digunakan bernilai 1/4 dari yang diberikan, agar terlihat perbedaan pada gelombang
```
dan hasil berkas gifnya adalah \
![![gelombang stasioner](https://user-images.githubusercontent.com/97928815/160538952-1ec69df3-985a-4645-a8cf-22b80adbf965.png)
]()
