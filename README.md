# 🐧 NASM Assembly Linux Notes 🐧
🐧 Assembly with **Linux** (Notes, **Syscalls**, **Protection Rings**) 🐧

## 🐧 System Calls Linux (Syscalls) 🐧

![System Calls Linux Assembly NASM ASM](Images/systemcalls_linux_kernel.png)

### ❓ What is a System Call? ❓

When you run a program which calls **open, fork, read, write** (and many others) you are making a **System Call**.

**System Calls** are how a program enters the kernel to perform some task. Programs use **System Calls** to perform a variety of operations such as: **creating processes, doing network and file IO**, and much more.

Example: A user running a word processor in **User Mode (Ring 3)** presses “save”: a **System Call** is made into **Kernel Mode (Ring 0)**, asking the **Kernel** to save the file.

## 📖 System Call Table (Syscall Table) 📖

<html xmlns:v="urn:schemas-microsoft-com:vml"
xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:x="urn:schemas-microsoft-com:office:excel"
xmlns="http://www.w3.org/TR/REC-html40">

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Excel.Sheet>
</head>

<body link=blue vlink=purple>

<table border=0 cellpadding=0 cellspacing=0 width=1022 style='border-collapse:
 collapse;table-layout:fixed;width:767pt'>
 <col width=29 style='mso-width-source:userset;mso-width-alt:1024;width:22pt'>
 <col width=83 style='width:62pt'>
 <col width=42 style='mso-width-source:userset;mso-width-alt:1507;width:32pt'>
 <col width=139 style='mso-width-source:userset;mso-width-alt:4949;width:104pt'>
 <col width=158 style='mso-width-source:userset;mso-width-alt:5632;width:119pt'>
 <col width=145 style='mso-width-source:userset;mso-width-alt:5148;width:109pt'>
 <col width=134 style='mso-width-source:userset;mso-width-alt:4778;width:101pt'>
 <col width=126 style='mso-width-source:userset;mso-width-alt:4465;width:94pt'>
 <col width=83 span=2 style='width:62pt'>
 <tr height=19 style='mso-height-source:userset;height:14.4pt'>
  <td rowspan=2 height=38 class=xl65 width=29 style='height:28.8pt;width:22pt'>#</td>
  <td rowspan=2 class=xl65 width=83 style='width:62pt'>Name</td>
  <td colspan=6 class=xl65 width=744 style='width:559pt'>Registers</td>
  <td width=83 style='width:62pt'></td>
  <td width=83 style='width:62pt'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl65 width=42 style='height:14.4pt;width:32pt'>eax</td>
  <td class=xl65 width=139 style='width:104pt'>ebx</td>
  <td class=xl65 width=158 style='width:119pt'>ecx</td>
  <td class=xl65 width=145 style='width:109pt'>edx</td>
  <td class=xl65 width=134 style='width:101pt'>esi</td>
  <td class=xl65 width=126 style='width:94pt'>edi</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>0</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/restart_syscall.2.html"
  target="_blank"> -->sys_restart_syscall<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x00</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>1</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/exit.2.html"
  target="_blank"> -->sys_exit<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x01</td>
  <td class=xl66 width=139 style='width:104pt'>int error_code</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>2</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fork.2.html"
  target="_blank"> -->sys_fork<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x02</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>3</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/read.2.html"
  target="_blank"> -->sys_read<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x03</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>size_t count</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>4</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/write.2.html"
  target="_blank"> -->sys_write<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x04</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>size_t count</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>5</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/open.2.html"
  target="_blank"> -->sys_open<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x05</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td class=xl66 width=145 style='width:109pt'>int mode</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>6</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/close.2.html"
  target="_blank"> -->sys_close<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x06</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>7</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/waitpid.2.html"
  target="_blank"> -->sys_waitpid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x07</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>int __user *stat_addr</td>
  <td class=xl66 width=145 style='width:109pt'>int options</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>8</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/creat.2.html"
  target="_blank"> -->sys_creat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x08</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=158 style='width:119pt'>int mode</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>9</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/link.2.html"
  target="_blank"> -->sys_link<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x09</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *oldname</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *newname</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>10</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/unlink.2.html"
  target="_blank"> -->sys_unlink<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0a</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>11</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/execve.2.html"
  target="_blank"> -->sys_execve<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0b</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *__user *</td>
  <td class=xl66 width=145 style='width:109pt'>char __user *__user *</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>12</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/chdir.2.html"
  target="_blank"> -->sys_chdir<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>13</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/time.2.html"
  target="_blank"> -->sys_time<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0d</td>
  <td class=xl66 width=139 style='width:104pt'>time_t __user *tloc</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>14</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mknod.2.html"
  target="_blank"> -->sys_mknod<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0e</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>int mode</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned dev</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>15</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/chmod.2.html"
  target="_blank"> -->sys_chmod<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x0f</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>mode_t mode</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>16</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lchown16.2.html"
  target="_blank"> -->sys_lchown16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>old_gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>17</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x11</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>18</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/stat.2.html"
  target="_blank"> -->sys_stat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct __old_kernel_stat _<span style='display:none'>_user *statbuf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>19</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lseek.2.html"
  target="_blank"> -->sys_lseek<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>off_t offset</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int origin</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>20</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getpid.2.html"
  target="_blank"> -->sys_getpid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>21</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mount.2.html"
  target="_blank"> -->sys_mount<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x15</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *dev_name</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *dir_name</td>
  <td class=xl66 width=145 style='width:109pt'>char __user *type</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long flags</td>
  <td class=xl66 width=126 style='width:94pt'>void __user *data</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>22</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/oldumount.2.html"
  target="_blank"> -->sys_oldumount<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x16</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>23</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setuid16.2.html"
  target="_blank"> -->sys_setuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x17</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t uid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>24</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getuid16.2.html"
  target="_blank"> -->sys_getuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x18</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>25</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/stime.2.html"
  target="_blank"> -->sys_stime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x19</td>
  <td class=xl66 width=139 style='width:104pt'>time_t __user *tptr</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>26</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ptrace.2.html"
  target="_blank"> -->sys_ptrace<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x1a</td>
  <td class=xl66 width=139 style='width:104pt'>long request</td>
  <td class=xl66 width=158 style='width:119pt'>long pid</td>
  <td class=xl66 width=145 style='width:109pt'>long addr</td>
  <td class=xl66 width=134 style='width:101pt'>long data</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>27</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/alarm.2.html"
  target="_blank"> -->sys_alarm<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x1b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int seconds</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>28</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fstat.2.html"
  target="_blank"> -->sys_fstat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x1c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td>struct __old_kernel_stat _<span style='display:none'>_user *statbuf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>29</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pause.2.html"
  target="_blank"> -->sys_pause<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x1d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>30</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/utime.2.html"
  target="_blank"> -->sys_utime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x1e</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct utimbuf __user *tim<span style='display:none'>es</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>31</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x1f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>32</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x20</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>33</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/access.2.html"
  target="_blank"> -->sys_access<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x21</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>int mode</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>34</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/nice.2.html"
  target="_blank"> -->sys_nice<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x22</td>
  <td class=xl66 width=139 style='width:104pt'>int increment</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>35</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x23</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>36</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sync.2.html"
  target="_blank"> -->sys_sync<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x24</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>37</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/kill.2.html"
  target="_blank"> -->sys_kill<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x25</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=158 style='width:119pt'>int sig</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>38</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rename.2.html"
  target="_blank"> -->sys_rename<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x26</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *oldname</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *newname</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>39</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mkdir.2.html"
  target="_blank"> -->sys_mkdir<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x27</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=158 style='width:119pt'>int mode</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>40</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rmdir.2.html"
  target="_blank"> -->sys_rmdir<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x28</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>41</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/dup.2.html"
  target="_blank"> -->sys_dup<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x29</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fildes</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>42</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pipe.2.html"
  target="_blank"> -->sys_pipe<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x2a</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *fildes</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>43</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/times.2.html"
  target="_blank"> -->sys_times<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x2b</td>
  <td class=xl66 width=139 style='width:104pt'>struct tms __user *tbuf</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>44</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x2c</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>45</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/brk.2.html"
  target="_blank"> -->sys_brk<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x2d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long brk</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>46</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setgid16.2.html"
  target="_blank"> -->sys_setgid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x2e</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t gid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>47</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getgid16.2.html"
  target="_blank"> -->sys_getgid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x2f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>48</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/signal.2.html"
  target="_blank"> -->sys_signal<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x30</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td class=xl66 width=158 style='width:119pt'>__sighandler_t handler</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>49</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/geteuid16.2.html"
  target="_blank"> -->sys_geteuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x31</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>50</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getegid16.2.html"
  target="_blank"> -->sys_getegid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x32</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>51</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/acct.2.html"
  target="_blank"> -->sys_acct<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x33</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>52</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/umount.2.html"
  target="_blank"> -->sys_umount<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x34</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>53</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x35</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>54</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ioctl.2.html"
  target="_blank"> -->sys_ioctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x36</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>55</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fcntl.2.html"
  target="_blank"> -->sys_fcntl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x37</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>56</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x38</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>57</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setpgid.2.html"
  target="_blank"> -->sys_setpgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x39</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>pid_t pgid</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>58</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x3a</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>59</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/olduname.2.html"
  target="_blank"> -->sys_olduname<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x3b</td>
  <td>struct oldold_utsname <span style='display:none'>__user *</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>60</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/umask.2.html"
  target="_blank"> -->sys_umask<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x3c</td>
  <td class=xl66 width=139 style='width:104pt'>int mask</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>61</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/chroot.2.html"
  target="_blank"> -->sys_chroot<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x3d</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>62</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ustat.2.html"
  target="_blank"> -->sys_ustat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x3e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned dev</td>
  <td>struct ustat __user *ubuf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>63</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/dup2.2.html"
  target="_blank"> -->sys_dup2<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x3f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int oldfd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int newfd</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>64</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getppid.2.html"
  target="_blank"> -->sys_getppid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x40</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>65</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getpgrp.2.html"
  target="_blank"> -->sys_getpgrp<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x41</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>66</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setsid.2.html"
  target="_blank"> -->sys_setsid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x42</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>67</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigaction.2.html"
  target="_blank"> -->sys_sigaction<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x43</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td>const struct old_sigaction <span style='display:none'>__user *act</span></td>
  <td>struct old_sigaction __u<span style='display:none'>ser *oact</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>68</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sgetmask.2.html"
  target="_blank"> -->sys_sgetmask<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x44</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>69</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ssetmask.2.html"
  target="_blank"> -->sys_ssetmask<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x45</td>
  <td class=xl66 width=139 style='width:104pt'>int newmask</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>70</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setreuid16.2.html"
  target="_blank"> -->sys_setreuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x46</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t ruid</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t euid</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>71</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setregid16.2.html"
  target="_blank"> -->sys_setregid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x47</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t rgid</td>
  <td class=xl66 width=158 style='width:119pt'>old_gid_t egid</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>72</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigsuspend.2.html"
  target="_blank"> -->sys_sigsuspend<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x48</td>
  <td class=xl66 width=139 style='width:104pt'>int history0</td>
  <td class=xl66 width=158 style='width:119pt'>int history1</td>
  <td class=xl66 width=145 style='width:109pt'>old_sigset_t mask</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>73</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigpending.2.html"
  target="_blank"> -->sys_sigpending<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x49</td>
  <td class=xl66 width=139 style='width:104pt'>old_sigset_t __user *set</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>74</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sethostname.2.html"
  target="_blank"> -->sys_sethostname<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4a</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>int len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>75</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setrlimit.2.html"
  target="_blank"> -->sys_setrlimit<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td>struct rlimit __user *rlim</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>76</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/old_getrlimit.2.html"
  target="_blank"> -->sys_old_getrlimit<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td>struct rlimit __user *rlim</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>77</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getrusage.2.html"
  target="_blank"> -->sys_getrusage<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4d</td>
  <td class=xl66 width=139 style='width:104pt'>int who</td>
  <td>struct rusage __user *ru</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>78</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/gettimeofday.2.html"
  target="_blank"> -->sys_gettimeofday<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4e</td>
  <td>struct timeval __user *t<span style='display:none'>v</span></td>
  <td class=xl66 width=158 style='width:119pt'>struct timezone __user *tz</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>79</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/settimeofday.2.html"
  target="_blank"> -->sys_settimeofday<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x4f</td>
  <td>struct timeval __user *t<span style='display:none'>v</span></td>
  <td class=xl66 width=158 style='width:119pt'>struct timezone __user *tz</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>80</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getgroups16.2.html"
  target="_blank"> -->sys_getgroups16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x50</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=158 style='width:119pt'>old_gid_t __user *grouplist</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>81</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setgroups16.2.html"
  target="_blank"> -->sys_setgroups16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x51</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=158 style='width:119pt'>old_gid_t __user *grouplist</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>82</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/old_select.2.html"
  target="_blank"> -->sys_old_select<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x52</td>
  <td>struct sel_arg_struct __<span style='display:none'>user *arg</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>83</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/symlink.2.html"
  target="_blank"> -->sys_symlink<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x53</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *old</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *new</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>84</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lstat.2.html"
  target="_blank"> -->sys_lstat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x54</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct __old_kernel_stat _<span style='display:none'>_user *statbuf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>85</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/readlink.2.html"
  target="_blank"> -->sys_readlink<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x55</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>int bufsiz</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>86</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/uselib.2.html"
  target="_blank"> -->sys_uselib<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x56</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *library</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>87</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/swapon.2.html"
  target="_blank"> -->sys_swapon<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x57</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *specialfile</td>
  <td class=xl66 width=158 style='width:119pt'>int swap_flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>88</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/reboot.2.html"
  target="_blank"> -->sys_reboot<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x58</td>
  <td class=xl66 width=139 style='width:104pt'>int magic1</td>
  <td class=xl66 width=158 style='width:119pt'>int magic2</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int cmd</td>
  <td class=xl66 width=134 style='width:101pt'>void __user *arg</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>89</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/old_readdir.2.html"
  target="_blank"> -->sys_old_readdir<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x59</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int</td>
  <td>struct old_linux_dirent __u<span style='display:none'>ser *</span></td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>90</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/old_mmap.2.html"
  target="_blank"> -->sys_old_mmap<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5a</td>
  <td>struct mmap_arg_struc<span style='display:none'>t __user *arg</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>91</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/munmap.2.html"
  target="_blank"> -->sys_munmap<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long addr</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>92</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/truncate.2.html"
  target="_blank"> -->sys_truncate<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>long length</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>93</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ftruncate.2.html"
  target="_blank"> -->sys_ftruncate<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long length</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>94</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchmod.2.html"
  target="_blank"> -->sys_fchmod<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>mode_t mode</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>95</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchown16.2.html"
  target="_blank"> -->sys_fchown16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x5f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>old_gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>96</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getpriority.2.html"
  target="_blank"> -->sys_getpriority<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x60</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=158 style='width:119pt'>int who</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>97</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setpriority.2.html"
  target="_blank"> -->sys_setpriority<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x61</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=158 style='width:119pt'>int who</td>
  <td class=xl66 width=145 style='width:109pt'>int niceval</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>98</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x62</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>99</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/statfs.2.html"
  target="_blank"> -->sys_statfs<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x63</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user * path</td>
  <td>struct statfs __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>100</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fstatfs.2.html"
  target="_blank"> -->sys_fstatfs<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x64</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td>struct statfs __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>101</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ioperm.2.html"
  target="_blank"> -->sys_ioperm<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x65</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long</td>
  <td class=xl66 width=145 style='width:109pt'>int</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>102</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/socketcall.2.html"
  target="_blank"> -->sys_socketcall<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x66</td>
  <td class=xl66 width=139 style='width:104pt'>int call</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long __user *args</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>103</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/syslog.2.html"
  target="_blank"> -->sys_syslog<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x67</td>
  <td class=xl66 width=139 style='width:104pt'>int type</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>int len</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>104</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setitimer.2.html"
  target="_blank"> -->sys_setitimer<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x68</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td>struct itimerval __user *val<span style='display:none'>ue</span></td>
  <td>struct itimerval __user *<span style='display:none'>ovalue</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>105</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getitimer.2.html"
  target="_blank"> -->sys_getitimer<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x69</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td>struct itimerval __user *val<span style='display:none'>ue</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>106</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/newstat.2.html"
  target="_blank"> -->sys_newstat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6a</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct stat __user *statbuf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>107</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/newlstat.2.html"
  target="_blank"> -->sys_newlstat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6b</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct stat __user *statbuf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>108</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/newfstat.2.html"
  target="_blank"> -->sys_newfstat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td>struct stat __user *statbuf</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>109</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/uname.2.html"
  target="_blank"> -->sys_uname<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6d</td>
  <td>struct old_utsname __u<span style='display:none'>ser *</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>110</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/iopl.2.html"
  target="_blank"> -->sys_iopl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>111</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/vhangup.2.html"
  target="_blank"> -->sys_vhangup<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x6f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>112</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x70</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>113</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/vm86old.2.html"
  target="_blank"> -->sys_vm86old<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x71</td>
  <td>struct vm86_struct __u<span style='display:none'>ser *</span></td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>114</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/wait4.2.html"
  target="_blank"> -->sys_wait4<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x72</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>int __user *stat_addr</td>
  <td class=xl66 width=145 style='width:109pt'>int options</td>
  <td>struct rusage __user *r<span style='display:none'>u</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>115</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/swapoff.2.html"
  target="_blank"> -->sys_swapoff<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x73</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *specialfile</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>116</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sysinfo.2.html"
  target="_blank"> -->sys_sysinfo<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x74</td>
  <td class=xl66 width=139 style='width:104pt'>struct sysinfo __user *info</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>117</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ipc.2.html"
  target="_blank"> -->sys_ipc<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x75</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>118</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fsync.2.html"
  target="_blank"> -->sys_fsync<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x76</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>119</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigreturn.2.html"
  target="_blank"> -->sys_sigreturn<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x77</td>
  <td>struct pt_regs *regs</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>120</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/clone.2.html"
  target="_blank"> -->sys_clone<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x78</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long</td>
  <td>struct pt_regs *</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>121</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setdomainname.2.html"
  target="_blank"> -->sys_setdomainname<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x79</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>int len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>122</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/newuname.2.html"
  target="_blank"> -->sys_newuname<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x7a</td>
  <td>struct new_utsname __<span style='display:none'>user *name</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>123</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/modify_ldt.2.html"
  target="_blank"> -->sys_modify_ldt<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x7b</td>
  <td class=xl66 width=139 style='width:104pt'>int</td>
  <td class=xl66 width=158 style='width:119pt'>void __user *</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>124</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/adjtimex.2.html"
  target="_blank"> -->sys_adjtimex<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x7c</td>
  <td>struct timex __user *tx<span style='display:none'>c_p</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>125</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mprotect.2.html"
  target="_blank"> -->sys_mprotect<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x7d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long prot</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>126</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigprocmask.2.html"
  target="_blank"> -->sys_sigprocmask<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x7e</td>
  <td class=xl66 width=139 style='width:104pt'>int how</td>
  <td class=xl66 width=158 style='width:119pt'>old_sigset_t __user *set</td>
  <td class=xl66 width=145 style='width:109pt'>old_sigset_t __user *oset</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>127</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x7f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>128</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/init_module.2.html"
  target="_blank"> -->sys_init_module<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x80</td>
  <td class=xl66 width=139 style='width:104pt'>void __user *umod</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long len</td>
  <td class=xl66 width=145 style='width:109pt'>const char __user *uargs</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>129</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/delete_module.2.html"
  target="_blank"> -->sys_delete_module<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x81</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name_user</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>130</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x82</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>131</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/quotactl.2.html"
  target="_blank"> -->sys_quotactl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x83</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int cmd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *special</td>
  <td class=xl66 width=145 style='width:109pt'>qid_t id</td>
  <td class=xl66 width=134 style='width:101pt'>void __user *addr</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>132</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getpgid.2.html"
  target="_blank"> -->sys_getpgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x84</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>133</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchdir.2.html"
  target="_blank"> -->sys_fchdir<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x85</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>134</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/bdflush.2.html"
  target="_blank"> -->sys_bdflush<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x86</td>
  <td class=xl66 width=139 style='width:104pt'>int func</td>
  <td class=xl66 width=158 style='width:119pt'>long data</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>135</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sysfs.2.html"
  target="_blank"> -->sys_sysfs<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x87</td>
  <td class=xl66 width=139 style='width:104pt'>int option</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long arg1</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg2</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>136</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/personality.2.html"
  target="_blank"> -->sys_personality<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x88</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int personality</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>137</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x89</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>138</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setfsuid16.2.html"
  target="_blank"> -->sys_setfsuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8a</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t uid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>139</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setfsgid16.2.html"
  target="_blank"> -->sys_setfsgid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8b</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t gid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>140</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/llseek.2.html"
  target="_blank"> -->sys_llseek<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long offset_high</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long offset_low</td>
  <td class=xl66 width=134 style='width:101pt'>loff_t __user *result</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned int origin</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>141</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getdents.2.html"
  target="_blank"> -->sys_getdents<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td>struct linux_dirent __user <span style='display:none'>*dirent</span></td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int count</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>142</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/select.2.html"
  target="_blank"> -->sys_select<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8e</td>
  <td class=xl66 width=139 style='width:104pt'>int n</td>
  <td class=xl66 width=158 style='width:119pt'>fd_set __user *inp</td>
  <td class=xl66 width=145 style='width:109pt'>fd_set __user *outp</td>
  <td class=xl66 width=134 style='width:101pt'>fd_set __user *exp</td>
  <td colspan=2 style='mso-ignore:colspan'>struct timeval __user *tvp</td>
  <td></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>143</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/flock.2.html"
  target="_blank"> -->sys_flock<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x8f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>144</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/msync.2.html"
  target="_blank"> -->sys_msync<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x90</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>int flags</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>145</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/readv.2.html"
  target="_blank"> -->sys_readv<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x91</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=158 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long vlen</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>146</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/writev.2.html"
  target="_blank"> -->sys_writev<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x92</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=158 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long vlen</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>147</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getsid.2.html"
  target="_blank"> -->sys_getsid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x93</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>148</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fdatasync.2.html"
  target="_blank"> -->sys_fdatasync<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x94</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>149</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sysctl.2.html"
  target="_blank"> -->sys_sysctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x95</td>
  <td>struct __sysctl_args __<span style='display:none'>user *args</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>150</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mlock.2.html"
  target="_blank"> -->sys_mlock<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x96</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>151</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/munlock.2.html"
  target="_blank"> -->sys_munlock<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x97</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>152</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mlockall.2.html"
  target="_blank"> -->sys_mlockall<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x98</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>153</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/munlockall.2.html"
  target="_blank"> -->sys_munlockall<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x99</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>154</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_setparam.2.html"
  target="_blank"> -->sys_sched_setparam<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9a</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td>struct sched_param __user<span style='display:none'> *param</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>155</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_getparam.2.html"
  target="_blank"> -->sys_sched_getparam<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9b</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td>struct sched_param __user<span style='display:none'> *param</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>156</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_setscheduler.2.html"
  target="_blank"> -->sys_sched_setscheduler<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9c</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>int policy</td>
  <td>struct sched_param __u<span style='display:none'>ser *param</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>157</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_getscheduler.2.html"
  target="_blank"> -->sys_sched_getscheduler<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9d</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>158</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_yield.2.html"
  target="_blank"> -->sys_sched_yield<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9e</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>159</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_get_priority_max.2.html"
  target="_blank"> -->sys_sched_get_priority_max<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x9f</td>
  <td class=xl66 width=139 style='width:104pt'>int policy</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>160</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_get_priority_min.2.html"
  target="_blank"> -->sys_sched_get_priority_min<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa0</td>
  <td class=xl66 width=139 style='width:104pt'>int policy</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>161</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_rr_get_interval.2.html"
  target="_blank"> -->sys_sched_rr_get_interval<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa1</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td>struct timespec __user *int<span style='display:none'>erval</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>162</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/nanosleep.2.html"
  target="_blank"> -->sys_nanosleep<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa2</td>
  <td>struct timespec __user <span style='display:none'>*rqtp</span></td>
  <td>struct timespec __user *r<span style='display:none'>mtp</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>163</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mremap.2.html"
  target="_blank"> -->sys_mremap<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa3</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long addr</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long old_len</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long new_len</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long flags</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long new_addr</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>164</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setresuid16.2.html"
  target="_blank"> -->sys_setresuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa4</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t ruid</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t euid</td>
  <td class=xl66 width=145 style='width:109pt'>old_uid_t suid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>165</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getresuid16.2.html"
  target="_blank"> -->sys_getresuid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa5</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t __user *ruid</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t __user *euid</td>
  <td class=xl66 width=145 style='width:109pt'>old_uid_t __user *suid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>166</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/vm86.2.html"
  target="_blank"> -->sys_vm86<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa6</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>167</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xa7</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>168</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/poll.2.html"
  target="_blank"> -->sys_poll<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa8</td>
  <td>struct pollfd __user *uf<span style='display:none'>ds</span></td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int nfds</td>
  <td class=xl66 width=145 style='width:109pt'>long timeout</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>169</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/nfsservctl.2.html"
  target="_blank"> -->sys_nfsservctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xa9</td>
  <td class=xl66 width=139 style='width:104pt'>int cmd</td>
  <td>struct nfsctl_arg __user *a<span style='display:none'>rg</span></td>
  <td class=xl66 width=145 style='width:109pt'>void __user *res</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>170</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setresgid16.2.html"
  target="_blank"> -->sys_setresgid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xaa</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t rgid</td>
  <td class=xl66 width=158 style='width:119pt'>old_gid_t egid</td>
  <td class=xl66 width=145 style='width:109pt'>old_gid_t sgid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>171</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getresgid16.2.html"
  target="_blank"> -->sys_getresgid16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xab</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t __user *rgid</td>
  <td class=xl66 width=158 style='width:119pt'>old_gid_t __user *egid</td>
  <td class=xl66 width=145 style='width:109pt'>old_gid_t __user *sgid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>172</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/prctl.2.html"
  target="_blank"> -->sys_prctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xac</td>
  <td class=xl66 width=139 style='width:104pt'>int option</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long arg2</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg3</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long arg4</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long arg5</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>173</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigreturn.2.html"
  target="_blank"> -->sys_rt_sigreturn<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xad</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>174</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigaction.2.html"
  target="_blank"> -->sys_rt_sigaction<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xae</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td>const struct sigaction __us<span style='display:none'>er *act</span></td>
  <td>struct sigaction __user *<span style='display:none'>oact</span></td>
  <td class=xl66 width=134 style='width:101pt'>size_t sigsetsize</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>175</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigprocmask.2.html"
  target="_blank"> -->sys_rt_sigprocmask<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xaf</td>
  <td class=xl66 width=139 style='width:104pt'>int how</td>
  <td class=xl66 width=158 style='width:119pt'>sigset_t __user *set</td>
  <td class=xl66 width=145 style='width:109pt'>sigset_t __user *oset</td>
  <td class=xl66 width=134 style='width:101pt'>size_t sigsetsize</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>176</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigpending.2.html"
  target="_blank"> -->sys_rt_sigpending<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb0</td>
  <td class=xl66 width=139 style='width:104pt'>sigset_t __user *set</td>
  <td class=xl66 width=158 style='width:119pt'>size_t sigsetsize</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>177</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigtimedwait.2.html"
  target="_blank"> -->sys_rt_sigtimedwait<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb1</td>
  <td class=xl66 width=139 style='width:104pt'>const sigset_t __user *uthese</td>
  <td class=xl66 width=158 style='width:119pt'>siginfo_t __user *uinfo</td>
  <td>const struct timespec __<span style='display:none'>user *uts</span></td>
  <td class=xl66 width=134 style='width:101pt'>size_t sigsetsize</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>178</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigqueueinfo.2.html"
  target="_blank"> -->sys_rt_sigqueueinfo<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb2</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=158 style='width:119pt'>int sig</td>
  <td class=xl66 width=145 style='width:109pt'>siginfo_t __user *uinfo</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>179</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_sigsuspend.2.html"
  target="_blank"> -->sys_rt_sigsuspend<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb3</td>
  <td class=xl66 width=139 style='width:104pt'>sigset_t __user *unewset</td>
  <td class=xl66 width=158 style='width:119pt'>size_t sigsetsize</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>180</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pread64.2.html"
  target="_blank"> -->sys_pread64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb4</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>size_t count</td>
  <td class=xl66 width=134 style='width:101pt'>loff_t pos</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>181</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pwrite64.2.html"
  target="_blank"> -->sys_pwrite64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>size_t count</td>
  <td class=xl66 width=134 style='width:101pt'>loff_t pos</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>182</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/chown16.2.html"
  target="_blank"> -->sys_chown16<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>old_gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>183</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getcwd.2.html"
  target="_blank"> -->sys_getcwd<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb7</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *buf</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long size</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>184</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/capget.2.html"
  target="_blank"> -->sys_capget<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb8</td>
  <td class=xl66 width=139 style='width:104pt'>cap_user_header_t header</td>
  <td class=xl66 width=158 style='width:119pt'>cap_user_data_t dataptr</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>185</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/capset.2.html"
  target="_blank"> -->sys_capset<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xb9</td>
  <td class=xl66 width=139 style='width:104pt'>cap_user_header_t header</td>
  <td class=xl66 width=158 style='width:119pt'>const cap_user_data_t data</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>186</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sigaltstack.2.html"
  target="_blank"> -->sys_sigaltstack<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xba</td>
  <td class=xl66 width=139 style='width:104pt'>const stack_t __user *</td>
  <td class=xl66 width=158 style='width:119pt'>stack_t __user *</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>187</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sendfile.2.html"
  target="_blank"> -->sys_sendfile<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xbb</td>
  <td class=xl66 width=139 style='width:104pt'>int out_fd</td>
  <td class=xl66 width=158 style='width:119pt'>int in_fd</td>
  <td class=xl66 width=145 style='width:109pt'>off_t __user *offset</td>
  <td class=xl66 width=134 style='width:101pt'>size_t count</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>188</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xbc</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>189</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xbd</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>190</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/vfork.2.html"
  target="_blank"> -->sys_vfork<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xbe</td>
  <td>struct pt_regs *</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>191</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getrlimit.2.html"
  target="_blank"> -->sys_getrlimit<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xbf</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td>struct rlimit __user *rlim</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>192</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mmap_pgoff.2.html"
  target="_blank"> -->sys_mmap_pgoff<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>193</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/truncate64.2.html"
  target="_blank"> -->sys_truncate64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc1</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t length</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>194</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ftruncate64.2.html"
  target="_blank"> -->sys_ftruncate64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc2</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t length</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>195</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/stat64.2.html"
  target="_blank"> -->sys_stat64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc3</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct stat64 __user *statb<span style='display:none'>uf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>196</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lstat64.2.html"
  target="_blank"> -->sys_lstat64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc4</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct stat64 __user *statb<span style='display:none'>uf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>197</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fstat64.2.html"
  target="_blank"> -->sys_fstat64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td>struct stat64 __user *statb<span style='display:none'>uf</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>198</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lchown.2.html"
  target="_blank"> -->sys_lchown<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>199</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getuid.2.html"
  target="_blank"> -->sys_getuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc7</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>200</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getgid.2.html"
  target="_blank"> -->sys_getgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc8</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>201</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/geteuid.2.html"
  target="_blank"> -->sys_geteuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xc9</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>202</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getegid.2.html"
  target="_blank"> -->sys_getegid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xca</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>203</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setreuid.2.html"
  target="_blank"> -->sys_setreuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xcb</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t ruid</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t euid</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>204</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setregid.2.html"
  target="_blank"> -->sys_setregid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xcc</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t rgid</td>
  <td class=xl66 width=158 style='width:119pt'>gid_t egid</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>205</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getgroups.2.html"
  target="_blank"> -->sys_getgroups<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xcd</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=158 style='width:119pt'>gid_t __user *grouplist</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>206</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setgroups.2.html"
  target="_blank"> -->sys_setgroups<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xce</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=158 style='width:119pt'>gid_t __user *grouplist</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>207</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchown.2.html"
  target="_blank"> -->sys_fchown<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xcf</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>208</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setresuid.2.html"
  target="_blank"> -->sys_setresuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd0</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t ruid</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t euid</td>
  <td class=xl66 width=145 style='width:109pt'>uid_t suid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>209</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getresuid.2.html"
  target="_blank"> -->sys_getresuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd1</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t __user *ruid</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t __user *euid</td>
  <td class=xl66 width=145 style='width:109pt'>uid_t __user *suid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>210</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setresgid.2.html"
  target="_blank"> -->sys_setresgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd2</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t rgid</td>
  <td class=xl66 width=158 style='width:119pt'>gid_t egid</td>
  <td class=xl66 width=145 style='width:109pt'>gid_t sgid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>211</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getresgid.2.html"
  target="_blank"> -->sys_getresgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd3</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t __user *rgid</td>
  <td class=xl66 width=158 style='width:119pt'>gid_t __user *egid</td>
  <td class=xl66 width=145 style='width:109pt'>gid_t __user *sgid</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>212</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/chown.2.html"
  target="_blank"> -->sys_chown<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd4</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=158 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=145 style='width:109pt'>gid_t group</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>213</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setuid.2.html"
  target="_blank"> -->sys_setuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd5</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t uid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>214</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setgid.2.html"
  target="_blank"> -->sys_setgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd6</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t gid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>215</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setfsuid.2.html"
  target="_blank"> -->sys_setfsuid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd7</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t uid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>216</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setfsgid.2.html"
  target="_blank"> -->sys_setfsgid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd8</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t gid</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>217</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pivot_root.2.html"
  target="_blank"> -->sys_pivot_root<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xd9</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *new_root</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *put_old</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>218</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mincore.2.html"
  target="_blank"> -->sys_mincore<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xda</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned char __user * vec</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>219</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/madvise.2.html"
  target="_blank"> -->sys_madvise<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xdb</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>int behavior</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>220</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getdents64.2.html"
  target="_blank"> -->sys_getdents64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xdc</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td>struct linux_dirent64 __use<span style='display:none'>r *dirent</span></td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int count</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>221</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fcntl64.2.html"
  target="_blank"> -->sys_fcntl64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xdd</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>222</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xde</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>223</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xdf</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>224</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/gettid.2.html"
  target="_blank"> -->sys_gettid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>225</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/readahead.2.html"
  target="_blank"> -->sys_readahead<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe1</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=145 style='width:109pt'>size_t count</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>226</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/setxattr.2.html"
  target="_blank"> -->sys_setxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe2</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>const void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>int flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>227</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lsetxattr.2.html"
  target="_blank"> -->sys_lsetxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe3</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>const void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>int flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>228</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fsetxattr.2.html"
  target="_blank"> -->sys_fsetxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe4</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>const void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>int flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>229</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getxattr.2.html"
  target="_blank"> -->sys_getxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe5</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>230</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lgetxattr.2.html"
  target="_blank"> -->sys_lgetxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>231</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fgetxattr.2.html"
  target="_blank"> -->sys_fgetxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe7</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>void __user *value</td>
  <td class=xl66 width=134 style='width:101pt'>size_t size</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>232</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/listxattr.2.html"
  target="_blank"> -->sys_listxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe8</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=145 style='width:109pt'>size_t size</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>233</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/llistxattr.2.html"
  target="_blank"> -->sys_llistxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xe9</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=145 style='width:109pt'>size_t size</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>234</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/flistxattr.2.html"
  target="_blank"> -->sys_flistxattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xea</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=145 style='width:109pt'>size_t size</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>235</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/removexattr.2.html"
  target="_blank"> -->sys_removexattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xeb</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>236</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lremovexattr.2.html"
  target="_blank"> -->sys_lremovexattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xec</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>237</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fremovexattr.2.html"
  target="_blank"> -->sys_fremovexattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xed</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>238</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/tkill.2.html"
  target="_blank"> -->sys_tkill<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xee</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=158 style='width:119pt'>int sig</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>239</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sendfile64.2.html"
  target="_blank"> -->sys_sendfile64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xef</td>
  <td class=xl66 width=139 style='width:104pt'>int out_fd</td>
  <td class=xl66 width=158 style='width:119pt'>int in_fd</td>
  <td class=xl66 width=145 style='width:109pt'>loff_t __user *offset</td>
  <td class=xl66 width=134 style='width:101pt'>size_t count</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>240</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/futex.2.html"
  target="_blank"> -->sys_futex<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>241</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_setaffinity.2.html"
  target="_blank"> -->sys_sched_setaffinity<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf1</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int len</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long __user
  *user_mask_ptr</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>242</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sched_getaffinity.2.html"
  target="_blank"> -->sys_sched_getaffinity<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf2</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int len</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long __user
  *user_mask_ptr</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>243</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/set_thread_area.2.html"
  target="_blank"> -->sys_set_thread_area<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf3</td>
  <td>struct user_desc __user<span style='display:none'> *</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>244</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/get_thread_area.2.html"
  target="_blank"> -->sys_get_thread_area<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf4</td>
  <td>struct user_desc __user<span style='display:none'> *</span></td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>245</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/io_setup.2.html"
  target="_blank"> -->sys_io_setup<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned nr_reqs</td>
  <td class=xl66 width=158 style='width:119pt'>aio_context_t __user *ctx</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>246</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/io_destroy.2.html"
  target="_blank"> -->sys_io_destroy<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf6</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>247</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/io_getevents.2.html"
  target="_blank"> -->sys_io_getevents<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf7</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx_id</td>
  <td class=xl66 width=158 style='width:119pt'>long min_nr</td>
  <td class=xl66 width=145 style='width:109pt'>long nr</td>
  <td>struct io_event __user <span style='display:none'>*events</span></td>
  <td colspan=2 style='mso-ignore:colspan'>struct timespec __user *timeout</td>
  <td></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>248</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/io_submit.2.html"
  target="_blank"> -->sys_io_submit<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf8</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t</td>
  <td class=xl66 width=158 style='width:119pt'>long</td>
  <td class=xl66 width=145 style='width:109pt'>struct iocb __user * __user *</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>249</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/io_cancel.2.html"
  target="_blank"> -->sys_io_cancel<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xf9</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx_id</td>
  <td class=xl66 width=158 style='width:119pt'>struct iocb __user *iocb</td>
  <td>struct io_event __user *<span style='display:none'>result</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>250</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fadvise64.2.html"
  target="_blank"> -->sys_fadvise64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xfa</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=145 style='width:109pt'>size_t len</td>
  <td class=xl66 width=134 style='width:101pt'>int advice</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>251</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0xfb</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>252</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/exit_group.2.html"
  target="_blank"> -->sys_exit_group<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xfc</td>
  <td class=xl66 width=139 style='width:104pt'>int error_code</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>253</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/lookup_dcookie.2.html"
  target="_blank"> -->sys_lookup_dcookie<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xfd</td>
  <td class=xl66 width=139 style='width:104pt'>u64 cookie64</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=145 style='width:109pt'>size_t len</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>254</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/epoll_create.2.html"
  target="_blank"> -->sys_epoll_create<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xfe</td>
  <td class=xl66 width=139 style='width:104pt'>int size</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>255</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/epoll_ctl.2.html"
  target="_blank"> -->sys_epoll_ctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0xff</td>
  <td class=xl66 width=139 style='width:104pt'>int epfd</td>
  <td class=xl66 width=158 style='width:119pt'>int op</td>
  <td class=xl66 width=145 style='width:109pt'>int fd</td>
  <td>struct epoll_event __u<span style='display:none'>ser *event</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>256</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/epoll_wait.2.html"
  target="_blank"> -->sys_epoll_wait<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x100</td>
  <td class=xl66 width=139 style='width:104pt'>int epfd</td>
  <td>struct epoll_event __user <span style='display:none'>*events</span></td>
  <td class=xl66 width=145 style='width:109pt'>int maxevents</td>
  <td class=xl66 width=134 style='width:101pt'>int timeout</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>257</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/remap_file_pages.2.html"
  target="_blank"> -->sys_remap_file_pages<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x101</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long size</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long prot</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long pgoff</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>258</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/set_tid_address.2.html"
  target="_blank"> -->sys_set_tid_address<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x102</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *tidptr</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>259</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timer_create.2.html"
  target="_blank"> -->sys_timer_create<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x103</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td>struct sigevent __user *tim<span style='display:none'>er_event_spec</span></td>
  <td class=xl66 width=145 style='width:109pt'>timer_t __user *
  created_timer_id</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>260</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timer_settime.2.html"
  target="_blank"> -->sys_timer_settime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x104</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td>const struct itimerspec _<span style='display:none'>_user *new_setting</span></td>
  <td>struct itimerspec __us<span style='display:none'>er *old_setting</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>261</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timer_gettime.2.html"
  target="_blank"> -->sys_timer_gettime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x105</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td>struct itimerspec __user *s<span style='display:none'>etting</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>262</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timer_getoverrun.2.html"
  target="_blank"> -->sys_timer_getoverrun<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x106</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>263</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timer_delete.2.html"
  target="_blank"> -->sys_timer_delete<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x107</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>264</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/clock_settime.2.html"
  target="_blank"> -->sys_clock_settime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x108</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td>const struct timespec __us<span style='display:none'>er *tp</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>265</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/clock_gettime.2.html"
  target="_blank"> -->sys_clock_gettime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x109</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td>struct timespec __user *tp</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>266</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/clock_getres.2.html"
  target="_blank"> -->sys_clock_getres<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10a</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td>struct timespec __user *tp</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>267</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/clock_nanosleep.2.html"
  target="_blank"> -->sys_clock_nanosleep<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10b</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td>const struct timespec __<span style='display:none'>user *rqtp</span></td>
  <td>struct timespec __user<span style='display:none'> *rmtp</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>268</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/statfs64.2.html"
  target="_blank"> -->sys_statfs64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=158 style='width:119pt'>size_t sz</td>
  <td>struct statfs64 __user *b<span style='display:none'>uf</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>269</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fstatfs64.2.html"
  target="_blank"> -->sys_fstatfs64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=158 style='width:119pt'>size_t sz</td>
  <td>struct statfs64 __user *b<span style='display:none'>uf</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>270</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/tgkill.2.html"
  target="_blank"> -->sys_tgkill<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10e</td>
  <td class=xl66 width=139 style='width:104pt'>int tgid</td>
  <td class=xl66 width=158 style='width:119pt'>int pid</td>
  <td class=xl66 width=145 style='width:109pt'>int sig</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>271</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/utimes.2.html"
  target="_blank"> -->sys_utimes<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x10f</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td>struct timeval __user *uti<span style='display:none'>mes</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>272</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fadvise64_64.2.html"
  target="_blank"> -->sys_fadvise64_64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x110</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=145 style='width:109pt'>loff_t len</td>
  <td class=xl66 width=134 style='width:101pt'>int advice</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>273</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x111</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>274</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mbind.2.html"
  target="_blank"> -->sys_mbind<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x112</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>275</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/get_mempolicy.2.html"
  target="_blank"> -->sys_get_mempolicy<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x113</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *policy</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long __user *nmask</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long maxnode</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long addr</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>276</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/set_mempolicy.2.html"
  target="_blank"> -->sys_set_mempolicy<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x114</td>
  <td class=xl66 width=139 style='width:104pt'>int mode</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long __user *nmask</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long maxnode</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>277</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_open.2.html"
  target="_blank"> -->sys_mq_open<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x115</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>int oflag</td>
  <td class=xl66 width=145 style='width:109pt'>mode_t mode</td>
  <td>struct mq_attr __user <span style='display:none'>*attr</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>278</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_unlink.2.html"
  target="_blank"> -->sys_mq_unlink<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x116</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>279</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_timedsend.2.html"
  target="_blank"> -->sys_mq_timedsend<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x117</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *msg_ptr</td>
  <td class=xl66 width=145 style='width:109pt'>size_t msg_len</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned int msg_prio</td>
  <td colspan=3 style='mso-ignore:colspan'>const struct timespec __user
  *abs_timeout</td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>280</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_timedreceive.2.html"
  target="_blank"> -->sys_mq_timedreceive<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x118</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *msg_ptr</td>
  <td class=xl66 width=145 style='width:109pt'>size_t msg_len</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned int __user *msg_prio</td>
  <td colspan=3 style='mso-ignore:colspan'>const struct timespec __user
  *abs_timeout</td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>281</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_notify.2.html"
  target="_blank"> -->sys_mq_notify<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x119</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td>const struct sigevent __use<span style='display:none'>r *notification</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>282</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mq_getsetattr.2.html"
  target="_blank"> -->sys_mq_getsetattr<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x11a</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td>const struct mq_attr __use<span style='display:none'>r *mqstat</span></td>
  <td>struct mq_attr __user *<span style='display:none'>omqstat</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>283</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/kexec_load.2.html"
  target="_blank"> -->sys_kexec_load<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x11b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long entry</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long nr_segments</td>
  <td>struct kexec_segment _<span style='display:none'>_user *segments</span></td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>284</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/waitid.2.html"
  target="_blank"> -->sys_waitid<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x11c</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=158 style='width:119pt'>pid_t pid</td>
  <td>struct siginfo __user *inf<span style='display:none'>op</span></td>
  <td class=xl66 width=134 style='width:101pt'>int options</td>
  <td colspan=2 style='mso-ignore:colspan'>struct rusage __user *ru</td>
  <td></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=29 style='height:43.2pt;
  width:22pt'>285</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=42 style='width:32pt'>0x11d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>286</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/add_key.2.html"
  target="_blank"> -->sys_add_key<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x11e</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *_type</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *_description</td>
  <td class=xl66 width=145 style='width:109pt'>const void __user *_payload</td>
  <td class=xl66 width=134 style='width:101pt'>size_t plen</td>
  <td class=xl66 width=126 style='width:94pt'>key_serial_t destringid</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>287</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/request_key.2.html"
  target="_blank"> -->sys_request_key<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x11f</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *_type</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *_description</td>
  <td class=xl66 width=145 style='width:109pt'>const char __user *_callout_info</td>
  <td class=xl66 width=134 style='width:101pt'>key_serial_t destringid</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>288</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/keyctl.2.html"
  target="_blank"> -->sys_keyctl<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x120</td>
  <td class=xl66 width=139 style='width:104pt'>int cmd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long arg2</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long arg3</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long arg4</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long arg5</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>289</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ioprio_set.2.html"
  target="_blank"> -->sys_ioprio_set<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x121</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=158 style='width:119pt'>int who</td>
  <td class=xl66 width=145 style='width:109pt'>int ioprio</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>290</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ioprio_get.2.html"
  target="_blank"> -->sys_ioprio_get<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x122</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=158 style='width:119pt'>int who</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>291</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/inotify_init.2.html"
  target="_blank"> -->sys_inotify_init<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x123</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>292</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/inotify_add_watch.2.html"
  target="_blank"> -->sys_inotify_add_watch<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x124</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *path</td>
  <td class=xl66 width=145 style='width:109pt'>u32 mask</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>293</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/inotify_rm_watch.2.html"
  target="_blank"> -->sys_inotify_rm_watch<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x125</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>__s32 wd</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>294</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/migrate_pages.2.html"
  target="_blank"> -->sys_migrate_pages<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x126</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned long maxnode</td>
  <td class=xl66 width=145 style='width:109pt'>const unsigned long __user *from</td>
  <td class=xl66 width=134 style='width:101pt'>const unsigned long __user *to</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>295</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/openat.2.html"
  target="_blank"> -->sys_openat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x127</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=145 style='width:109pt'>int flags</td>
  <td class=xl66 width=134 style='width:101pt'>int mode</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>296</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mkdirat.2.html"
  target="_blank"> -->sys_mkdirat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x128</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user * pathname</td>
  <td class=xl66 width=145 style='width:109pt'>int mode</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>297</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/mknodat.2.html"
  target="_blank"> -->sys_mknodat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x129</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user * filename</td>
  <td class=xl66 width=145 style='width:109pt'>int mode</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned dev</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>298</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchownat.2.html"
  target="_blank"> -->sys_fchownat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12a</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=145 style='width:109pt'>uid_t user</td>
  <td class=xl66 width=134 style='width:101pt'>gid_t group</td>
  <td class=xl66 width=126 style='width:94pt'>int flag</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>299</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/futimesat.2.html"
  target="_blank"> -->sys_futimesat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12b</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *filename</td>
  <td>struct timeval __user *u<span style='display:none'>times</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>300</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fstatat64.2.html"
  target="_blank"> -->sys_fstatat64<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12c</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *filename</td>
  <td>struct stat64 __user *sta<span style='display:none'>tbuf</span></td>
  <td class=xl66 width=134 style='width:101pt'>int flag</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>301</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/unlinkat.2.html"
  target="_blank"> -->sys_unlinkat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12d</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user * pathname</td>
  <td class=xl66 width=145 style='width:109pt'>int flag</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>302</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/renameat.2.html"
  target="_blank"> -->sys_renameat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12e</td>
  <td class=xl66 width=139 style='width:104pt'>int olddfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user * oldname</td>
  <td class=xl66 width=145 style='width:109pt'>int newdfd</td>
  <td class=xl66 width=134 style='width:101pt'>const char __user * newname</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>303</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/linkat.2.html"
  target="_blank"> -->sys_linkat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x12f</td>
  <td class=xl66 width=139 style='width:104pt'>int olddfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *oldname</td>
  <td class=xl66 width=145 style='width:109pt'>int newdfd</td>
  <td class=xl66 width=134 style='width:101pt'>const char __user *newname</td>
  <td class=xl66 width=126 style='width:94pt'>int flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>304</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/symlinkat.2.html"
  target="_blank"> -->sys_symlinkat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x130</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user * oldname</td>
  <td class=xl66 width=158 style='width:119pt'>int newdfd</td>
  <td class=xl66 width=145 style='width:109pt'>const char __user * newname</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>305</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/readlinkat.2.html"
  target="_blank"> -->sys_readlinkat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x131</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *path</td>
  <td class=xl66 width=145 style='width:109pt'>char __user *buf</td>
  <td class=xl66 width=134 style='width:101pt'>int bufsiz</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>306</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fchmodat.2.html"
  target="_blank"> -->sys_fchmodat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x132</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user * filename</td>
  <td class=xl66 width=145 style='width:109pt'>mode_t mode</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>307</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/faccessat.2.html"
  target="_blank"> -->sys_faccessat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x133</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=145 style='width:109pt'>int mode</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>308</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pselect6.2.html"
  target="_blank"> -->sys_pselect6<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x134</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>309</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/ppoll.2.html"
  target="_blank"> -->sys_ppoll<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x135</td>
  <td>struct pollfd __user *uf<span style='display:none'>ds</span></td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int nfds</td>
  <td>struct timespec __user *<span style='display:none'>tsp</span></td>
  <td class=xl66 width=134 style='width:101pt'>const sigset_t __user *sigmask</td>
  <td class=xl66 width=126 style='width:94pt'>size_t sigsetsize</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>310</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/unshare.2.html"
  target="_blank"> -->sys_unshare<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x136</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long unshare_flags</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>311</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/set_robust_list.2.html"
  target="_blank"> -->sys_set_robust_list<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x137</td>
  <td>struct robust_list_head <span style='display:none'>__user *head</span></td>
  <td class=xl66 width=158 style='width:119pt'>size_t len</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>312</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/get_robust_list.2.html"
  target="_blank"> -->sys_get_robust_list<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x138</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td>struct robust_list_head __<span style='display:none'>user * __user
  *head_ptr</span></td>
  <td class=xl66 width=145 style='width:109pt'>size_t __user *len_ptr</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>313</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/splice.2.html"
  target="_blank"> -->sys_splice<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x139</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>314</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/sync_file_range.2.html"
  target="_blank"> -->sys_sync_file_range<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13a</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=145 style='width:109pt'>loff_t nbytes</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned int flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>315</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/tee.2.html"
  target="_blank"> -->sys_tee<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13b</td>
  <td class=xl66 width=139 style='width:104pt'>int fdin</td>
  <td class=xl66 width=158 style='width:119pt'>int fdout</td>
  <td class=xl66 width=145 style='width:109pt'>size_t len</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned int flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>316</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/vmsplice.2.html"
  target="_blank"> -->sys_vmsplice<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13c</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>const struct iovec __user *iov</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long nr_segs</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned int flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>317</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/move_pages.2.html"
  target="_blank"> -->sys_move_pages<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>318</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/getcpu.2.html"
  target="_blank"> -->sys_getcpu<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned __user *cpu</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned __user *node</td>
  <td>struct getcpu_cache __u<span style='display:none'>ser *cache</span></td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>319</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/epoll_pwait.2.html"
  target="_blank"> -->sys_epoll_pwait<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x13f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>320</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/utimensat.2.html"
  target="_blank"> -->sys_utimensat<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x140</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=158 style='width:119pt'>char __user *filename</td>
  <td>struct timespec __user *<span style='display:none'>utimes</span></td>
  <td class=xl66 width=134 style='width:101pt'>int flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>321</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/signalfd.2.html"
  target="_blank"> -->sys_signalfd<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x141</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=158 style='width:119pt'>sigset_t __user *user_mask</td>
  <td class=xl66 width=145 style='width:109pt'>size_t sizemask</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>322</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timerfd_create.2.html"
  target="_blank"> -->sys_timerfd_create<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x142</td>
  <td class=xl66 width=139 style='width:104pt'>int clockid</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>323</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/eventfd.2.html"
  target="_blank"> -->sys_eventfd<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x143</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int count</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>324</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/fallocate.2.html"
  target="_blank"> -->sys_fallocate<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x144</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=158 style='width:119pt'>int mode</td>
  <td class=xl66 width=145 style='width:109pt'>loff_t offset</td>
  <td class=xl66 width=134 style='width:101pt'>loff_t len</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>325</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timerfd_settime.2.html"
  target="_blank"> -->sys_timerfd_settime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x145</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td>const struct itimerspec _<span style='display:none'>_user *utmr</span></td>
  <td>struct itimerspec __us<span style='display:none'>er *otmr</span></td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>326</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/timerfd_gettime.2.html"
  target="_blank"> -->sys_timerfd_gettime<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x146</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td>struct itimerspec __user *<span style='display:none'>otmr</span></td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>327</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/signalfd4.2.html"
  target="_blank"> -->sys_signalfd4<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x147</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=158 style='width:119pt'>sigset_t __user *user_mask</td>
  <td class=xl66 width=145 style='width:109pt'>size_t sizemask</td>
  <td class=xl66 width=134 style='width:101pt'>int flags</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>328</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/eventfd2.2.html"
  target="_blank"> -->sys_eventfd2<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x148</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int count</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>329</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/epoll_create1.2.html"
  target="_blank"> -->sys_epoll_create1<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x149</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>330</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/dup3.2.html"
  target="_blank"> -->sys_dup3<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14a</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int oldfd</td>
  <td class=xl66 width=158 style='width:119pt'>unsigned int newfd</td>
  <td class=xl66 width=145 style='width:109pt'>int flags</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=29 style='height:14.4pt;
  width:22pt'>331</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pipe2.2.html"
  target="_blank"> -->sys_pipe2<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14b</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *fildes</td>
  <td class=xl66 width=158 style='width:119pt'>int flags</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>332</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/inotify_init1.2.html"
  target="_blank"> -->sys_inotify_init1<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14c</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=158 style='width:119pt'>-</td>
  <td class=xl66 width=145 style='width:109pt'>-</td>
  <td class=xl66 width=134 style='width:101pt'>-</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>333</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/preadv.2.html"
  target="_blank"> -->sys_preadv<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=158 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long vlen</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long pos_l</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long pos_h</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>334</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/pwritev.2.html"
  target="_blank"> -->sys_pwritev<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=158 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=145 style='width:109pt'>unsigned long vlen</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned long pos_l</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long pos_h</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>335</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/rt_tgsigqueueinfo.2.html"
  target="_blank"> -->sys_rt_tgsigqueueinfo<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x14f</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t tgid</td>
  <td class=xl66 width=158 style='width:119pt'>pid_t pid</td>
  <td class=xl66 width=145 style='width:109pt'>int sig</td>
  <td class=xl66 width=134 style='width:101pt'>siginfo_t __user *uinfo</td>
  <td class=xl66 width=126 style='width:94pt'>-</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>336</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/perf_event_open.2.html"
  target="_blank"> -->sys_perf_event_open<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x150</td>
  <td>struct perf_event_attr <span style='display:none'>__user *attr_uptr</span></td>
  <td class=xl66 width=158 style='width:119pt'>pid_t pid</td>
  <td class=xl66 width=145 style='width:109pt'>int cpu</td>
  <td class=xl66 width=134 style='width:101pt'>int group_fd</td>
  <td class=xl66 width=126 style='width:94pt'>unsigned long flags</td>
  <td colspan=2 style='mso-ignore:colspan'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=29 style='height:28.8pt;
  width:22pt'>337</td>
  <td class=xl67 width=83 style='width:62pt'><!-- <a
  href="a/doc/man-pages/online/pages/man2/recvmmsg.2.html"
  target="_blank"> -->sys_recvmmsg<!-- </a> --></td>
  <td class=xl66 width=42 style='width:32pt'>0x151</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td>struct mmsghdr __user *m<span style='display:none'>sg</span></td>
  <td class=xl66 width=145 style='width:109pt'>unsigned int vlen</td>
  <td class=xl66 width=134 style='width:101pt'>unsigned flags</td>
  <td colspan=2 style='mso-ignore:colspan'>struct timespec __user *timeout</td>
  <td></td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=29 style='width:22pt'></td>
  <td width=83 style='width:62pt'></td>
  <td width=42 style='width:32pt'></td>
  <td width=139 style='width:104pt'></td>
  <td width=158 style='width:119pt'></td>
  <td width=145 style='width:109pt'></td>
  <td width=134 style='width:101pt'></td>
  <td width=126 style='width:94pt'></td>
  <td width=83 style='width:62pt'></td>
  <td width=83 style='width:62pt'></td>
 </tr>
 <![endif]>
</table>

</body>

</html>


## 🔧 Simple System Call Example calling SYS_WRITE (kernel opcode 4) 🔧
At Line **17**: **mov     eax, 4      ; invoke SYS_WRITE (kernel opcode 4)**
```
; Hello World Program
; Compile with: nasm -f elf helloworld.asm
; Link with (64 bit systems require elf_i386 option): ld -m elf_i386 helloworld.o -o helloworld
; Run with: ./helloworld
 
SECTION .data
msg     db      'Hello World!', 0Ah     ; assign msg variable with your message string
 
SECTION .text
global  _start
 
_start:
 
    mov     edx, 13     ; number of bytes to write - one for each letter plus 0Ah (line feed character)
    mov     ecx, msg    ; move the memory address of our message string into ecx
    mov     ebx, 1      ; write to the STDOUT file
    mov     eax, 4      ; invoke SYS_WRITE (kernel opcode 4)
    int     80h
```
## 🐧 Protection Rings / Privilege Levels 🐧
The x86-64 CPUs have a concept called **Privilege Levels**. (also often called **Protection Rings**)</br>
**Linux** only uses **Ring 0** and **3** for **Kernel Mode (Ring 0)** and **User Mode (Ring 3)**. Thus, all user mode processes, running when the system is in any run level execute in **Ring 3**, until they make a **System Call** into kernel code, which transitions the cpu to **Ring 0**.

1. The **Kernel** runs at the most **privileged level**, called **Ring 0**. **User programs** run at **Ring 3**.
2. **Ring 0** can execute any system instruction and is given full trust.
3. To enter **Kernel Mode (Ring 0)**, you must perform a **System Call**. (Another Way to use **Kernel Mode (Ring 0)** is by writing **Linux Kernel Modules** in C.) </br> *Additional Info: In Windows you usually program a **driver** in C to use Kernel Mode (Ring 0) and like **Linux**, Windows only uses **Ring 0** and **3** too.*

![Privilege_Levels System Calls Linux Assembly NASM ASM](Images/privilege_levels_linux.png)
