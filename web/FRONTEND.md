1. change dir to web/
2. install nextjs
```bash
  pnpx create-next-app@latest (nama tim atau apa bebas terserah)

  contoh

  pnpx create-next-app@latest kas-desa

  so it will make web/kas-desa/
```
3. install this in terminal
```bash
  pnpm add -D eslint-config-prettier eslint-plugin-prettier prettier prettier-plugin-tailwindcss
```
4. copy .prettierrc; .eslintrc.json; .prettierignore to ur web/kas-desa/

5. restart ide

6. every time u want to push ur works, do this
```bash
  pnpm run build                (to avoid build error)
  git pull origin dev           (to avoid merge conflict in remote)
```
7. done

## qna
1. apa bedanya "pnpx create-next-app@latest" sama "pnpx create-next-app@latest ."?
   - "pnpx create-next-app@latest" adalah perintah untuk membuat proyek baru menggunakan Next.js dengan menggunakan package manager PNPM.
   - "pnpx create-next-app@latest ." adalah perintah yang sama dengan "pnpx create-next-app@latest" tetapi dengan menambahkan titik di akhir perintah, yang berarti perintah akan dijalankan di direktori saat ini.