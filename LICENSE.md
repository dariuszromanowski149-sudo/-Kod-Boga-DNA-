# Kod Boga DNA – Wzór 83111184

To mój wzór rezonujący z Fibonacciego i YHWH (10-5-6-5). Modeluje spiralę w DNA.

## Użycie
Uruchom 'moj_kod.py' w Pythonie – wygeneruje 3D helisę.

## Licencja
MIT – wolne użycie z uznaniem autorstwa.
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Twój kod
user_code = [8, 3, 1, 1, 1, 1, 8, 4]

# YHWH
yhwh = [10, 5, 6, 5]

# Fibonacciego
fib = [0, 1, 1, 2, 3, 5, 8, 13]

# Parametry 3D helisy
theta = np.linspace(0, 4*np.pi, 100)
z = np.linspace(0, 10, 100)
r = 1

# Nit 1 (Fib – niebieska)
x1 = r * np.cos(theta)
y1 = r * np.sin(theta)
z1 = z

# Nit 2 (twój kod – czerwona)
theta2 = theta + np.pi
x2 = r * np.cos(theta2)
y2 = r * np.sin(theta2)
z2 = z

# Nit 3 (YHWH – zielona)
theta3 = theta + np.pi / 2
x3 = r * np.cos(theta3)
y3 = r * np.sin(theta3)
z3 = z

fig = plt.figure(figsize=(12, 9))
ax = fig.add_subplot(111, projection='3d')

ax.plot(x1, y1, z1, 'b-', linewidth=2, label='Nit 1 (Fibonacciego)')
ax.plot(x2, y2, z2, 'r-', linewidth=2, label='Nit 2 (Twój kod 83111184)')
ax.plot(x3, y3, z3, 'g-', linewidth=2, label='Nit 3 (YHWH 10-5-6-5)')

# Etykiety Fib na nit 1
positions_fib = np.linspace(0, len(z)-1, len(fib), dtype=int)
for i, num in enumerate(fib):
    ax.text(x1[positions_fib[i]], y1[positions_fib[i]], z1[positions_fib[i]], str(num), color='blue', fontsize=10)

# Etykiety twojego kodu na nit 2
positions_user = np.linspace(0, len(z)-1, len(user_code), dtype=int)
for i, num in enumerate(user_code):
    ax.text(x2[positions_user[i]], y2[positions_user[i]], z2[positions_user[i]], str(num), color='red', fontsize=10)

# Etykiety YHWH na nit 3
positions_yhwh = np.linspace(0, len(z)-1, len(yhwh), dtype=int)
for i, num in enumerate(yhwh):
    ax.text(x3[positions_yhwh[i]], y3[positions_yhwh[i]], z3[positions_yhwh[i]], str(num), color='green', fontsize=10)

# Równanie liczb
sum_user = sum(user_code)  # 27
sum_yhwh = sum(yhwh)  # 26
sum_fib = sum(fib)  # 33
ax.text(0, 0, 5, f'Równanie: 27 (twój) ≈ 26 (YHWH) +1; Fib suma 33', color='black', fontsize=12)

ax.set_title('3D Model helisy z kodem 83111184, YHWH i Fibonaccim')
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z (Å)')
ax.legend()
ax.view_init(elev=20, azim=45)

# Zapisz w Pobranych
download_path = '/storage/emulated/0/Download/3d_model_combined.png'
plt.savefig(download_path, dpi=300, bbox_inches='tight')
print(f"Plik zapisany w: {download_path}")

plt.show()
