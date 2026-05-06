# 1. Find Bug :

<img width="1846" height="767" alt="image" src="https://github.com/user-attachments/assets/8a30b376-c5fd-4ecd-8ed0-f3ac08713785" />

- Buffer overflow ở `read`

- leak stdout không biết của hàm nào

# 2. Idea :

<img width="1300" height="267" alt="image" src="https://github.com/user-attachments/assets/03d9d775-065d-4a00-8c66-1cfd6ee293ca" />

- Thấy NX bật -> r2shellcode ko được

- ROPChain thuần ko đủ thanh ghi

- Có thể dùng one_gadget hoặc ret2libc

<img width="2538" height="939" alt="image" src="https://github.com/user-attachments/assets/305c2d81-fc3f-423d-bffe-5e7ffc136452" />

- Nhận thấy offset = 40 nghĩa là chỉ overwrite được 6byte saved RIP -> one_gadget

# 3. Exploit :

<img width="2240" height="770" alt="image" src="https://github.com/user-attachments/assets/6b64669f-cd1e-4f87-a36d-8e5687e33a31" />

- Vậy là đã biết địa chỉ được leak ra của hàm nào

<img width="1012" height="197" alt="image" src="https://github.com/user-attachments/assets/798ab9c5-786f-4261-b90b-30be0341c57f" />

- Viết script xác định libc base

- 
