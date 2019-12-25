# 🐧 NASM Assembly Linux Notes 🐧
🐧 Assembly with Linux (Notes, Syscalls) 🐧

## 🐧 System Calls Linux (Syscalls) 🐧

<html xmlns:v="urn:schemas-microsoft-com:vml"
xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:x="urn:schemas-microsoft-com:office:excel"
xmlns="http://www.w3.org/TR/REC-html40">

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Excel.Sheet>
<meta name=Generator content="Microsoft Excel 14">
<link rel=File-List href=filelist.xml>
<link rel=Stylesheet href=stylesheet.css>
<!--table
	{mso-displayed-decimal-separator:"\.";
	mso-displayed-thousand-separator:"\0027";}
@page
	{margin:.79in .7in .79in .7in;
	mso-header-margin:.3in;
	mso-footer-margin:.3in;}
-->
</head>

<body link=blue vlink=purple>

<table border=0 cellpadding=0 cellspacing=0 width=1117 style='border-collapse:
 collapse;table-layout:fixed;width:836pt'>
 <col width=83 span=3 style='width:62pt'>
 <col width=139 style='mso-width-source:userset;mso-width-alt:4949;width:104pt'>
 <col width=159 style='mso-width-source:userset;mso-width-alt:5660;width:119pt'>
 <col width=151 style='mso-width-source:userset;mso-width-alt:5376;width:113pt'>
 <col width=138 style='mso-width-source:userset;mso-width-alt:4892;width:103pt'>
 <col width=127 style='mso-width-source:userset;mso-width-alt:4522;width:95pt'>
 <col width=154 style='mso-width-source:userset;mso-width-alt:5489;width:116pt'>
 <tr height=19 style='height:14.4pt'>
  <td height=19 colspan=9 style='height:14.4pt;mso-ignore:colspan'></td>
 </tr>
 <tr height=19 style='mso-height-source:userset;height:14.4pt'>
  <td rowspan=2 height=38 class=xl65 width=83 style='height:28.8pt;width:62pt'>#</td>
  <td rowspan=2 class=xl65 width=83 style='width:62pt'>Name</td>
  <td colspan=6 class=xl65 width=797 style='width:596pt'>Registers</td>
  <td rowspan=2 class=xl65 width=154 style='width:116pt'>Definition</td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl65 width=83 style='height:14.4pt;width:62pt'>eax</td>
  <td class=xl65 width=139 style='width:104pt'>ebx</td>
  <td class=xl65 width=159 style='width:119pt'>ecx</td>
  <td class=xl65 width=151 style='width:113pt'>edx</td>
  <td class=xl65 width=138 style='width:103pt'>esi</td>
  <td class=xl65 width=127 style='width:95pt'>edi</td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>0</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/restart_syscall.2.html"
  target="_blank">sys_restart_syscall</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x00</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2058"
  target="_blank">kernel/signal.c:2058</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>1</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/exit.2.html"
  target="_blank">sys_exit</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x01</td>
  <td class=xl66 width=139 style='width:104pt'>int error_code</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exit.c?v=2.6.35#L1046"
  target="_blank">kernel/exit.c:1046</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>2</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fork.2.html"
  target="_blank">sys_fork</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x02</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L716"
  target="_blank">arch/alpha/kernel/entry.S:716</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>3</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/read.2.html"
  target="_blank">sys_read</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x03</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>size_t count</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L391"
  target="_blank">fs/read_write.c:391</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>4</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/write.2.html"
  target="_blank">sys_write</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x04</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>size_t count</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L408"
  target="_blank">fs/read_write.c:408</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>5</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/open.2.html"
  target="_blank">sys_open</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x05</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl66 width=151 style='width:113pt'>int mode</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L900"
  target="_blank">fs/open.c:900</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>6</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/close.2.html"
  target="_blank">sys_close</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x06</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L969"
  target="_blank">fs/open.c:969</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>7</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/waitpid.2.html"
  target="_blank">sys_waitpid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x07</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>int __user *stat_addr</td>
  <td class=xl66 width=151 style='width:113pt'>int options</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exit.c?v=2.6.35#L1771"
  target="_blank">kernel/exit.c:1771</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>8</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/creat.2.html"
  target="_blank">sys_creat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x08</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=159 style='width:119pt'>int mode</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L933"
  target="_blank">fs/open.c:933</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>9</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/link.2.html"
  target="_blank">sys_link</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x09</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *oldname</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *newname</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2520"
  target="_blank">fs/namei.c:2520</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>10</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/unlink.2.html"
  target="_blank">sys_unlink</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0a</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2352"
  target="_blank">fs/namei.c:2352</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>11</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/execve.2.html"
  target="_blank">sys_execve</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0b</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *__user *</td>
  <td class=xl66 width=151 style='width:113pt'>char __user *__user *</td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L925"
  target="_blank">arch/alpha/kernel/entry.S:925</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>12</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/chdir.2.html"
  target="_blank">sys_chdir</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L361"
  target="_blank">fs/open.c:361</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>13</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/time.2.html"
  target="_blank">sys_time</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0d</td>
  <td class=xl66 width=139 style='width:104pt'>time_t __user *tloc</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L855"
  target="_blank">kernel/posix-timers.c:855</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>14</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mknod.2.html"
  target="_blank">sys_mknod</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0e</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>int mode</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned dev</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2067"
  target="_blank">fs/namei.c:2067</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>15</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/chmod.2.html"
  target="_blank">sys_chmod</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x0f</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>mode_t mode</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L507"
  target="_blank">fs/open.c:507</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>16</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lchown16.2.html"
  target="_blank">sys_lchown16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>old_gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L27"
  target="_blank">kernel/uid16.c:27</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>17</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x11</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>18</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/stat.2.html"
  target="_blank">sys_stat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/arm/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct __old_kernel_stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L150"
  target="_blank">fs/stat.c:150</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>19</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lseek.2.html"
  target="_blank">sys_lseek</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>off_t offset</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int origin</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L167"
  target="_blank">fs/read_write.c:167</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>20</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getpid.2.html"
  target="_blank">sys_getpid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1337"
  target="_blank">kernel/timer.c:1337</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>21</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mount.2.html"
  target="_blank">sys_mount</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x15</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *dev_name</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *dir_name</td>
  <td class=xl66 width=151 style='width:113pt'>char __user *type</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long flags</td>
  <td class=xl66 width=127 style='width:95pt'>void __user *data</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namespace.c?v=2.6.35#L2118"
  target="_blank">fs/namespace.c:2118</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>22</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/oldumount.2.html"
  target="_blank">sys_oldumount</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x16</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namespace.c?v=2.6.35#L1171"
  target="_blank">fs/namespace.c:1171</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>23</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setuid16.2.html"
  target="_blank">sys_setuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x17</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t uid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L67"
  target="_blank">kernel/uid16.c:67</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>24</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getuid16.2.html"
  target="_blank">sys_getuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x18</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L212"
  target="_blank">kernel/uid16.c:212</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>25</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/stime.2.html"
  target="_blank">sys_stime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x19</td>
  <td class=xl66 width=139 style='width:104pt'>time_t __user *tptr</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/time.c?v=2.6.35#L81"
  target="_blank">kernel/time.c:81</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>26</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ptrace.2.html"
  target="_blank">sys_ptrace</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x1a</td>
  <td class=xl66 width=139 style='width:104pt'>long request</td>
  <td class=xl66 width=159 style='width:119pt'>long pid</td>
  <td class=xl66 width=151 style='width:113pt'>long addr</td>
  <td class=xl66 width=138 style='width:103pt'>long data</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/ptrace.c?v=2.6.35#L688"
  target="_blank">kernel/ptrace.c:688</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>27</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/alarm.2.html"
  target="_blank">sys_alarm</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x1b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int seconds</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1314"
  target="_blank">kernel/timer.c:1314</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>28</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fstat.2.html"
  target="_blank">sys_fstat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x1c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/arm/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct __old_kernel_stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L174"
  target="_blank">fs/stat.c:174</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>29</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pause.2.html"
  target="_blank">sys_pause</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x1d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2700"
  target="_blank">kernel/signal.c:2700</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>30</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/utime.2.html"
  target="_blank">sys_utime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x1e</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/utime.h?v=2.6.35#L6"
  target="_blank">struct utimbuf __user *times</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/utimes.c?v=2.6.35#L27"
  target="_blank">fs/utimes.c:27</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>31</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x1f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>32</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x20</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>33</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/access.2.html"
  target="_blank">sys_access</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x21</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>int mode</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L356"
  target="_blank">fs/open.c:356</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>34</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/nice.2.html"
  target="_blank">sys_nice</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x22</td>
  <td class=xl66 width=139 style='width:104pt'>int increment</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4282"
  target="_blank">kernel/sched.c:4282</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>35</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x23</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=19 style='height:14.4pt'>
  <td height=19 class=xl66 align=right width=83 style='height:14.4pt;
  width:62pt'>36</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sync.2.html"
  target="_blank">sys_sync</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x24</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/sync.c?v=2.6.35#L98"
  target="_blank">fs/sync.c:98</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>37</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/kill.2.html"
  target="_blank">sys_kill</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x25</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=159 style='width:119pt'>int sig</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2317"
  target="_blank">kernel/signal.c:2317</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>38</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rename.2.html"
  target="_blank">sys_rename</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x26</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *oldname</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *newname</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2765"
  target="_blank">fs/namei.c:2765</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>39</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mkdir.2.html"
  target="_blank">sys_mkdir</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x27</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=159 style='width:119pt'>int mode</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2130"
  target="_blank">fs/namei.c:2130</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>40</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rmdir.2.html"
  target="_blank">sys_rmdir</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x28</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *pathname</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2244"
  target="_blank">fs/namei.c:2244</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>41</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/dup.2.html"
  target="_blank">sys_dup</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x29</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fildes</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/fcntl.c?v=2.6.35#L131"
  target="_blank">fs/fcntl.c:131</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>42</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pipe.2.html"
  target="_blank">sys_pipe</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x2a</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *fildes</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/pipe.c?v=2.6.35#L1117"
  target="_blank">fs/pipe.c:1117</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>43</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/times.2.html"
  target="_blank">sys_times</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x2b</td>
  <td class=xl66 width=139 style='width:104pt'>struct tms __user *tbuf</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L896"
  target="_blank">kernel/sys.c:896</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>44</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x2c</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>45</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/brk.2.html"
  target="_blank">sys_brk</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x2d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long brk</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mmap.c?v=2.6.35#L245"
  target="_blank">mm/mmap.c:245</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>46</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setgid16.2.html"
  target="_blank">sys_setgid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x2e</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t gid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L51"
  target="_blank">kernel/uid16.c:51</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>47</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getgid16.2.html"
  target="_blank">sys_getgid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x2f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L222"
  target="_blank">kernel/uid16.c:222</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>48</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/signal.2.html"
  target="_blank">sys_signal</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x30</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td class=xl66 width=159 style='width:119pt'>__sighandler_t handler</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2683"
  target="_blank">kernel/signal.c:2683</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>49</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/geteuid16.2.html"
  target="_blank">sys_geteuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x31</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L217"
  target="_blank">kernel/uid16.c:217</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>50</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getegid16.2.html"
  target="_blank">sys_getegid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x32</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L227"
  target="_blank">kernel/uid16.c:227</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>51</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/acct.2.html"
  target="_blank">sys_acct</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x33</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/acct.c?v=2.6.35#L274"
  target="_blank">kernel/acct.c:274</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>52</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/umount.2.html"
  target="_blank">sys_umount</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x34</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namespace.c?v=2.6.35#L1132"
  target="_blank">fs/namespace.c:1132</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>53</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x35</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>54</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ioctl.2.html"
  target="_blank">sys_ioctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x36</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/ioctl.c?v=2.6.35#L613"
  target="_blank">fs/ioctl.c:613</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>55</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fcntl.2.html"
  target="_blank">sys_fcntl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x37</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/fcntl.c?v=2.6.35#L429"
  target="_blank">fs/fcntl.c:429</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>56</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x38</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>57</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setpgid.2.html"
  target="_blank">sys_setpgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x39</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>pid_t pgid</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L921"
  target="_blank">kernel/sys.c:921</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>58</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x3a</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>59</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/olduname.2.html"
  target="_blank">sys_olduname</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x3b</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/utsname.h?v=2.6.35#L6"
  target="_blank">struct oldold_utsname __user *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1132"
  target="_blank">kernel/sys.c:1132</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>60</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/umask.2.html"
  target="_blank">sys_umask</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x3c</td>
  <td class=xl66 width=139 style='width:104pt'>int mask</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1460"
  target="_blank">kernel/sys.c:1460</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>61</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/chroot.2.html"
  target="_blank">sys_chroot</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x3d</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L408"
  target="_blank">fs/open.c:408</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>62</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ustat.2.html"
  target="_blank">sys_ustat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x3e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned dev</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/types.h?v=2.6.35#L200"
  target="_blank">struct ustat __user *ubuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/statfs.c?v=2.6.35#L175"
  target="_blank">fs/statfs.c:175</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>63</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/dup2.2.html"
  target="_blank">sys_dup2</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x3f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int oldfd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int newfd</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/fcntl.c?v=2.6.35#L116"
  target="_blank">fs/fcntl.c:116</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>64</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getppid.2.html"
  target="_blank">sys_getppid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x40</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1348"
  target="_blank">kernel/timer.c:1348</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>65</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getpgrp.2.html"
  target="_blank">sys_getpgrp</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x41</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1020"
  target="_blank">kernel/sys.c:1020</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>66</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setsid.2.html"
  target="_blank">sys_setsid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x42</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1055"
  target="_blank">kernel/sys.c:1055</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>67</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigaction.2.html"
  target="_blank">sys_sigaction</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x43</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/arm/include/asm/signal.h?v=2.6.35#L117"
  target="_blank">const struct old_sigaction __user *act</a></td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/arm/include/asm/signal.h?v=2.6.35#L117"
  target="_blank">struct old_sigaction __user *oact</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/kernel/signal.c?v=2.6.35#L300"
  target="_blank">arch/mips/kernel/signal.c:300</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>68</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sgetmask.2.html"
  target="_blank">sys_sgetmask</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x44</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2657"
  target="_blank">kernel/signal.c:2657</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>69</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ssetmask.2.html"
  target="_blank">sys_ssetmask</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x45</td>
  <td class=xl66 width=139 style='width:104pt'>int newmask</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2663"
  target="_blank">kernel/signal.c:2663</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>70</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setreuid16.2.html"
  target="_blank">sys_setreuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x46</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t ruid</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t euid</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L59"
  target="_blank">kernel/uid16.c:59</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>71</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setregid16.2.html"
  target="_blank">sys_setregid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x47</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t rgid</td>
  <td class=xl66 width=159 style='width:119pt'>old_gid_t egid</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L43"
  target="_blank">kernel/uid16.c:43</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>72</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigsuspend.2.html"
  target="_blank">sys_sigsuspend</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x48</td>
  <td class=xl66 width=139 style='width:104pt'>int history0</td>
  <td class=xl66 width=159 style='width:119pt'>int history1</td>
  <td class=xl66 width=151 style='width:113pt'>old_sigset_t mask</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/s390/kernel/signal.c?v=2.6.35#L58"
  target="_blank">arch/s390/kernel/signal.c:58</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>73</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigpending.2.html"
  target="_blank">sys_sigpending</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x49</td>
  <td class=xl66 width=139 style='width:104pt'>old_sigset_t __user *set</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2562"
  target="_blank">kernel/signal.c:2562</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>74</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sethostname.2.html"
  target="_blank">sys_sethostname</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4a</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>int len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1165"
  target="_blank">kernel/sys.c:1165</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>75</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setrlimit.2.html"
  target="_blank">sys_setrlimit</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L41"
  target="_blank">struct rlimit __user *rlim</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1275"
  target="_blank">kernel/sys.c:1275</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>76</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/old_getrlimit.2.html"
  target="_blank">sys_old_getrlimit</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L41"
  target="_blank">struct rlimit __user *rlim</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1256"
  target="_blank">kernel/sys.c:1256</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>77</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getrusage.2.html"
  target="_blank">sys_getrusage</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4d</td>
  <td class=xl66 width=139 style='width:104pt'>int who</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L22"
  target="_blank">struct rusage __user *ru</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1452"
  target="_blank">kernel/sys.c:1452</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>78</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/gettimeofday.2.html"
  target="_blank">sys_gettimeofday</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4e</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L20"
  target="_blank">struct timeval __user *tv</a></td>
  <td class=xl66 width=159 style='width:119pt'>struct timezone __user *tz</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/time.c?v=2.6.35#L101"
  target="_blank">kernel/time.c:101</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>79</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/settimeofday.2.html"
  target="_blank">sys_settimeofday</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x4f</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L20"
  target="_blank">struct timeval __user *tv</a></td>
  <td class=xl66 width=159 style='width:119pt'>struct timezone __user *tz</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/time.c?v=2.6.35#L185"
  target="_blank">kernel/time.c:185</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>80</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getgroups16.2.html"
  target="_blank">sys_getgroups16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x50</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=159 style='width:119pt'>old_gid_t __user *grouplist</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L164"
  target="_blank">kernel/uid16.c:164</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>81</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setgroups16.2.html"
  target="_blank">sys_setgroups16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x51</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=159 style='width:119pt'>old_gid_t __user *grouplist</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L187"
  target="_blank">kernel/uid16.c:187</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>82</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/old_select.2.html"
  target="_blank">sys_old_select</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x52</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L695"
  target="_blank">struct sel_arg_struct __user *arg</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L701"
  target="_blank">fs/select.c:701</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>83</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/symlink.2.html"
  target="_blank">sys_symlink</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x53</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *old</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *new</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2419"
  target="_blank">fs/namei.c:2419</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>84</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lstat.2.html"
  target="_blank">sys_lstat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x54</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/arm/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct __old_kernel_stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L162"
  target="_blank">fs/stat.c:162</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>85</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/readlink.2.html"
  target="_blank">sys_readlink</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x55</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>int bufsiz</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L311"
  target="_blank">fs/stat.c:311</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>86</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/uselib.2.html"
  target="_blank">sys_uselib</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x56</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *library</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/exec.c?v=2.6.35#L107"
  target="_blank">fs/exec.c:107</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>87</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/swapon.2.html"
  target="_blank">sys_swapon</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x57</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *specialfile</td>
  <td class=xl66 width=159 style='width:119pt'>int swap_flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/swapfile.c?v=2.6.35#L1793"
  target="_blank">mm/swapfile.c:1793</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>88</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/reboot.2.html"
  target="_blank">sys_reboot</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x58</td>
  <td class=xl66 width=139 style='width:104pt'>int magic1</td>
  <td class=xl66 width=159 style='width:119pt'>int magic2</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int cmd</td>
  <td class=xl66 width=138 style='width:103pt'>void __user *arg</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L368"
  target="_blank">kernel/sys.c:368</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>89</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/old_readdir.2.html"
  target="_blank">sys_old_readdir</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x59</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/fs/readdir.c?v=2.6.35#L61"
  target="_blank">struct old_linux_dirent __user *</a></td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/readdir.c?v=2.6.35#L105"
  target="_blank">fs/readdir.c:105</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>90</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/old_mmap.2.html"
  target="_blank">sys_old_mmap</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5a</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/mm/mmap.c?v=2.6.35#L1132"
  target="_blank">struct mmap_arg_struct __user *arg</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mmap.c?v=2.6.35#L1141"
  target="_blank">mm/mmap.c:1141</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>91</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/munmap.2.html"
  target="_blank">sys_munmap</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long addr</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mmap.c?v=2.6.35#L2109"
  target="_blank">mm/mmap.c:2109</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>92</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/truncate.2.html"
  target="_blank">sys_truncate</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>long length</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L127"
  target="_blank">fs/open.c:127</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>93</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ftruncate.2.html"
  target="_blank">sys_ftruncate</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long length</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L178"
  target="_blank">fs/open.c:178</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>94</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchmod.2.html"
  target="_blank">sys_fchmod</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>mode_t mode</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L436"
  target="_blank">fs/open.c:436</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>95</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchown16.2.html"
  target="_blank">sys_fchown16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x5f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>old_gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L35"
  target="_blank">kernel/uid16.c:35</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>96</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getpriority.2.html"
  target="_blank">sys_getpriority</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x60</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=159 style='width:119pt'>int who</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L216"
  target="_blank">kernel/sys.c:216</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>97</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setpriority.2.html"
  target="_blank">sys_setpriority</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x61</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=159 style='width:119pt'>int who</td>
  <td class=xl66 width=151 style='width:113pt'>int niceval</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L149"
  target="_blank">kernel/sys.c:149</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>98</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x62</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>99</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/statfs.2.html"
  target="_blank">sys_statfs</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x63</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user * path</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/include/asm/statfs.h?v=2.6.35#L22"
  target="_blank">struct statfs __user *buf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/statfs.c?v=2.6.35#L102"
  target="_blank">fs/statfs.c:102</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>100</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fstatfs.2.html"
  target="_blank">sys_fstatfs</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x64</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/include/asm/statfs.h?v=2.6.35#L22"
  target="_blank">struct statfs __user *buf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/statfs.c?v=2.6.35#L136"
  target="_blank">fs/statfs.c:136</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>101</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ioperm.2.html"
  target="_blank">sys_ioperm</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x65</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long</td>
  <td class=xl66 width=151 style='width:113pt'>int</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>102</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/socketcall.2.html"
  target="_blank">sys_socketcall</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x66</td>
  <td class=xl66 width=139 style='width:104pt'>int call</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long __user *args</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/net/socket.c?v=2.6.35#L2210"
  target="_blank">net/socket.c:2210</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>103</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/syslog.2.html"
  target="_blank">sys_syslog</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x67</td>
  <td class=xl66 width=139 style='width:104pt'>int type</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>int len</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/printk.c?v=2.6.35#L412"
  target="_blank">kernel/printk.c:412</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>104</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setitimer.2.html"
  target="_blank">sys_setitimer</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x68</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L263"
  target="_blank">struct itimerval __user *value</a></td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L263"
  target="_blank">struct itimerval __user *ovalue</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/itimer.c?v=2.6.35#L279"
  target="_blank">kernel/itimer.c:279</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>105</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getitimer.2.html"
  target="_blank">sys_getitimer</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x69</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L263"
  target="_blank">struct itimerval __user *value</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/itimer.c?v=2.6.35#L103"
  target="_blank">kernel/itimer.c:103</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>106</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/newstat.2.html"
  target="_blank">sys_newstat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6a</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L237"
  target="_blank">fs/stat.c:237</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>107</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/newlstat.2.html"
  target="_blank">sys_newlstat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6b</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L247"
  target="_blank">fs/stat.c:247</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>108</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/newfstat.2.html"
  target="_blank">sys_newfstat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L4"
  target="_blank">struct stat __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L273"
  target="_blank">fs/stat.c:273</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>109</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/uname.2.html"
  target="_blank">sys_uname</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6d</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/utsname.h?v=2.6.35#L16"
  target="_blank">struct old_utsname __user *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1115"
  target="_blank">kernel/sys.c:1115</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>110</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/iopl.2.html"
  target="_blank">sys_iopl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>111</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/vhangup.2.html"
  target="_blank">sys_vhangup</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x6f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L1008"
  target="_blank">fs/open.c:1008</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>112</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x70</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>113</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/vm86old.2.html"
  target="_blank">sys_vm86old</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x71</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/x86/include/asm/vm86.h?v=2.6.35#L96"
  target="_blank">struct vm86_struct __user *</a></td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>114</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/wait4.2.html"
  target="_blank">sys_wait4</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x72</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>int __user *stat_addr</td>
  <td class=xl66 width=151 style='width:113pt'>int options</td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L22"
  target="_blank">struct rusage __user *ru</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exit.c?v=2.6.35#L1726"
  target="_blank">kernel/exit.c:1726</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>115</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/swapoff.2.html"
  target="_blank">sys_swapoff</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x73</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *specialfile</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/swapfile.c?v=2.6.35#L1533"
  target="_blank">mm/swapfile.c:1533</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>116</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sysinfo.2.html"
  target="_blank">sys_sysinfo</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x74</td>
  <td class=xl66 width=139 style='width:104pt'>struct sysinfo __user *info</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1565"
  target="_blank">kernel/timer.c:1565</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>117</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ipc.2.html"
  target="_blank">sys_ipc</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x75</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/syscall.c?v=2.6.35#L16"
  target="_blank">ipc/syscall.c:16</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>118</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fsync.2.html"
  target="_blank">sys_fsync</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x76</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/sync.c?v=2.6.35#L221"
  target="_blank">fs/sync.c:221</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>119</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigreturn.2.html"
  target="_blank">sys_sigreturn</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x77</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *regs</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L758"
  target="_blank">arch/alpha/kernel/entry.S:758</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>120</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/clone.2.html"
  target="_blank">sys_clone</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x78</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L733"
  target="_blank">arch/alpha/kernel/entry.S:733</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>121</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setdomainname.2.html"
  target="_blank">sys_setdomainname</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x79</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>int len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1214"
  target="_blank">kernel/sys.c:1214</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>122</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/newuname.2.html"
  target="_blank">sys_newuname</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x7a</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/utsname.h?v=2.6.35#L24"
  target="_blank">struct new_utsname __user *name</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1097"
  target="_blank">kernel/sys.c:1097</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>123</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/modify_ldt.2.html"
  target="_blank">sys_modify_ldt</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x7b</td>
  <td class=xl66 width=139 style='width:104pt'>int</td>
  <td class=xl66 width=159 style='width:119pt'>void __user *</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>124</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/adjtimex.2.html"
  target="_blank">sys_adjtimex</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x7c</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/timex.h?v=2.6.35#L64"
  target="_blank">struct timex __user *txc_p</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/time.c?v=2.6.35#L206"
  target="_blank">kernel/time.c:206</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>125</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mprotect.2.html"
  target="_blank">sys_mprotect</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x7d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long prot</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mprotect.c?v=2.6.35#L221"
  target="_blank">mm/mprotect.c:221</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>126</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigprocmask.2.html"
  target="_blank">sys_sigprocmask</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x7e</td>
  <td class=xl66 width=139 style='width:104pt'>int how</td>
  <td class=xl66 width=159 style='width:119pt'>old_sigset_t __user *set</td>
  <td class=xl66 width=151 style='width:113pt'>old_sigset_t __user *oset</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2573"
  target="_blank">kernel/signal.c:2573</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>127</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x7f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>128</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/init_module.2.html"
  target="_blank">sys_init_module</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x80</td>
  <td class=xl66 width=139 style='width:104pt'>void __user *umod</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long len</td>
  <td class=xl66 width=151 style='width:113pt'>const char __user *uargs</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/module.c?v=2.6.35#L2611"
  target="_blank">kernel/module.c:2611</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>129</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/delete_module.2.html"
  target="_blank">sys_delete_module</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x81</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name_user</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/module.c?v=2.6.35#L720"
  target="_blank">kernel/module.c:720</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>130</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x82</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>131</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/quotactl.2.html"
  target="_blank">sys_quotactl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x83</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int cmd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *special</td>
  <td class=xl66 width=151 style='width:113pt'>qid_t id</td>
  <td class=xl66 width=138 style='width:103pt'>void __user *addr</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/quota/quota.c?v=2.6.35#L333"
  target="_blank">fs/quota/quota.c:333</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>132</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getpgid.2.html"
  target="_blank">sys_getpgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x84</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L990"
  target="_blank">kernel/sys.c:990</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>133</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchdir.2.html"
  target="_blank">sys_fchdir</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x85</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L382"
  target="_blank">fs/open.c:382</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>134</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/bdflush.2.html"
  target="_blank">sys_bdflush</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x86</td>
  <td class=xl66 width=139 style='width:104pt'>int func</td>
  <td class=xl66 width=159 style='width:119pt'>long data</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/buffer.c?v=2.6.35#L3278"
  target="_blank">fs/buffer.c:3278</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>135</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sysfs.2.html"
  target="_blank">sys_sysfs</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x87</td>
  <td class=xl66 width=139 style='width:104pt'>int option</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long arg1</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg2</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/filesystems.c?v=2.6.35#L182"
  target="_blank">fs/filesystems.c:182</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>136</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/personality.2.html"
  target="_blank">sys_personality</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x88</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int personality</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exec_domain.c?v=2.6.35#L191"
  target="_blank">kernel/exec_domain.c:191</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>137</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x89</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>138</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setfsuid16.2.html"
  target="_blank">sys_setfsuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8a</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t uid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L118"
  target="_blank">kernel/uid16.c:118</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>139</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setfsgid16.2.html"
  target="_blank">sys_setfsgid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8b</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t gid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L126"
  target="_blank">kernel/uid16.c:126</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>140</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/llseek.2.html"
  target="_blank">sys_llseek</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8c</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long offset_high</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long offset_low</td>
  <td class=xl66 width=138 style='width:103pt'>loff_t __user *result</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned int origin</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L191"
  target="_blank">fs/read_write.c:191</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>141</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getdents.2.html"
  target="_blank">sys_getdents</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/fs/readdir.c?v=2.6.35#L135"
  target="_blank">struct linux_dirent __user *dirent</a></td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int count</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/readdir.c?v=2.6.35#L191"
  target="_blank">fs/readdir.c:191</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>142</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/select.2.html"
  target="_blank">sys_select</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8e</td>
  <td class=xl66 width=139 style='width:104pt'>int n</td>
  <td class=xl66 width=159 style='width:119pt'>fd_set __user *inp</td>
  <td class=xl66 width=151 style='width:113pt'>fd_set __user *outp</td>
  <td class=xl66 width=138 style='width:103pt'>fd_set __user *exp</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L20"
  target="_blank">struct timeval __user *tvp</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L596"
  target="_blank">fs/select.c:596</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>143</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/flock.2.html"
  target="_blank">sys_flock</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x8f</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/locks.c?v=2.6.35#L1569"
  target="_blank">fs/locks.c:1569</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>144</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/msync.2.html"
  target="_blank">sys_msync</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x90</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>int flags</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/msync.c?v=2.6.35#L31"
  target="_blank">mm/msync.c:31</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>145</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/readv.2.html"
  target="_blank">sys_readv</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x91</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=159 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long vlen</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L711"
  target="_blank">fs/read_write.c:711</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>146</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/writev.2.html"
  target="_blank">sys_writev</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x92</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=159 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long vlen</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L732"
  target="_blank">fs/read_write.c:732</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>147</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getsid.2.html"
  target="_blank">sys_getsid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x93</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1027"
  target="_blank">kernel/sys.c:1027</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>148</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fdatasync.2.html"
  target="_blank">sys_fdatasync</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x94</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/sync.c?v=2.6.35#L226"
  target="_blank">fs/sync.c:226</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>149</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sysctl.2.html"
  target="_blank">sys_sysctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x95</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/sysctl.h?v=2.6.35#L36"
  target="_blank">struct __sysctl_args __user *args</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sysctl_binary.c?v=2.6.35#L1462"
  target="_blank">kernel/sysctl_binary.c:1462</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>150</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mlock.2.html"
  target="_blank">sys_mlock</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x96</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mlock.c?v=2.6.35#L491"
  target="_blank">mm/mlock.c:491</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>151</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/munlock.2.html"
  target="_blank">sys_munlock</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x97</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mlock.c?v=2.6.35#L519"
  target="_blank">mm/mlock.c:519</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>152</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mlockall.2.html"
  target="_blank">sys_mlockall</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x98</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mlock.c?v=2.6.35#L556"
  target="_blank">mm/mlock.c:556</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>153</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/munlockall.2.html"
  target="_blank">sys_munlockall</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x99</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mlock.c?v=2.6.35#L584"
  target="_blank">mm/mlock.c:584</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>154</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_setparam.2.html"
  target="_blank">sys_sched_setparam</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9a</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/sched.h?v=2.6.35#L46"
  target="_blank">struct sched_param __user *param</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4616"
  target="_blank">kernel/sched.c:4616</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>155</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_getparam.2.html"
  target="_blank">sys_sched_getparam</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9b</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/sched.h?v=2.6.35#L46"
  target="_blank">struct sched_param __user *param</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4651"
  target="_blank">kernel/sched.c:4651</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>156</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_setscheduler.2.html"
  target="_blank">sys_sched_setscheduler</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9c</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>int policy</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/sched.h?v=2.6.35#L46"
  target="_blank">struct sched_param __user *param</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4601"
  target="_blank">kernel/sched.c:4601</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>157</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_getscheduler.2.html"
  target="_blank">sys_sched_getscheduler</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9d</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4625"
  target="_blank">kernel/sched.c:4625</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>158</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_yield.2.html"
  target="_blank">sys_sched_yield</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9e</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4851"
  target="_blank">kernel/sched.c:4851</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>159</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_get_priority_max.2.html"
  target="_blank">sys_sched_get_priority_max</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x9f</td>
  <td class=xl66 width=139 style='width:104pt'>int policy</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4989"
  target="_blank">kernel/sched.c:4989</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>160</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_get_priority_min.2.html"
  target="_blank">sys_sched_get_priority_min</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa0</td>
  <td class=xl66 width=139 style='width:104pt'>int policy</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L5014"
  target="_blank">kernel/sched.c:5014</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>161</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_rr_get_interval.2.html"
  target="_blank">sys_sched_rr_get_interval</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa1</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *interval</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L5039"
  target="_blank">kernel/sched.c:5039</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>162</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/nanosleep.2.html"
  target="_blank">sys_nanosleep</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa2</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *rqtp</a></td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *rmtp</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/hrtimer.c?v=2.6.35#L1606"
  target="_blank">kernel/hrtimer.c:1606</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>163</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mremap.2.html"
  target="_blank">sys_mremap</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa3</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long addr</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long old_len</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long new_len</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long flags</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long new_addr</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mremap.c?v=2.6.35#L510"
  target="_blank">mm/mremap.c:510</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>164</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setresuid16.2.html"
  target="_blank">sys_setresuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa4</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t ruid</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t euid</td>
  <td class=xl66 width=151 style='width:113pt'>old_uid_t suid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L75"
  target="_blank">kernel/uid16.c:75</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>165</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getresuid16.2.html"
  target="_blank">sys_getresuid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa5</td>
  <td class=xl66 width=139 style='width:104pt'>old_uid_t __user *ruid</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t __user *euid</td>
  <td class=xl66 width=151 style='width:113pt'>old_uid_t __user *suid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L84"
  target="_blank">kernel/uid16.c:84</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>166</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/vm86.2.html"
  target="_blank">sys_vm86</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa6</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>167</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xa7</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>168</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/poll.2.html"
  target="_blank">sys_poll</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa8</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/asm-generic/poll.h?v=2.6.35#L31"
  target="_blank">struct pollfd __user *ufds</a></td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int nfds</td>
  <td class=xl66 width=151 style='width:113pt'>long timeout</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L915"
  target="_blank">fs/select.c:915</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>169</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/nfsservctl.2.html"
  target="_blank">sys_nfsservctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xa9</td>
  <td class=xl66 width=139 style='width:104pt'>int cmd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/nfsd/syscall.h?v=2.6.35#L77"
  target="_blank">struct nfsctl_arg __user *arg</a></td>
  <td class=xl66 width=151 style='width:113pt'>void __user *res</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/nfsctl.c?v=2.6.35#L86"
  target="_blank">fs/nfsctl.c:86</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>170</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setresgid16.2.html"
  target="_blank">sys_setresgid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xaa</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t rgid</td>
  <td class=xl66 width=159 style='width:119pt'>old_gid_t egid</td>
  <td class=xl66 width=151 style='width:113pt'>old_gid_t sgid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L96"
  target="_blank">kernel/uid16.c:96</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>171</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getresgid16.2.html"
  target="_blank">sys_getresgid16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xab</td>
  <td class=xl66 width=139 style='width:104pt'>old_gid_t __user *rgid</td>
  <td class=xl66 width=159 style='width:119pt'>old_gid_t __user *egid</td>
  <td class=xl66 width=151 style='width:113pt'>old_gid_t __user *sgid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L106"
  target="_blank">kernel/uid16.c:106</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>172</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/prctl.2.html"
  target="_blank">sys_prctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xac</td>
  <td class=xl66 width=139 style='width:104pt'>int option</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long arg2</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg3</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long arg4</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long arg5</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1466"
  target="_blank">kernel/sys.c:1466</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>173</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigreturn.2.html"
  target="_blank">sys_rt_sigreturn</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xad</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L771"
  target="_blank">arch/alpha/kernel/entry.S:771</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>174</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigaction.2.html"
  target="_blank">sys_rt_sigaction</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xae</td>
  <td class=xl66 width=139 style='width:104pt'>int sig</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/signal.h?v=2.6.35#L123"
  target="_blank">const struct sigaction __user *act</a></td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/signal.h?v=2.6.35#L123"
  target="_blank">struct sigaction __user *oact</a></td>
  <td class=xl66 width=138 style='width:103pt'>size_t sigsetsize</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2624"
  target="_blank">kernel/signal.c:2624</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>175</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigprocmask.2.html"
  target="_blank">sys_rt_sigprocmask</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xaf</td>
  <td class=xl66 width=139 style='width:104pt'>int how</td>
  <td class=xl66 width=159 style='width:119pt'>sigset_t __user *set</td>
  <td class=xl66 width=151 style='width:113pt'>sigset_t __user *oset</td>
  <td class=xl66 width=138 style='width:103pt'>size_t sigsetsize</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2111"
  target="_blank">kernel/signal.c:2111</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>176</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigpending.2.html"
  target="_blank">sys_rt_sigpending</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb0</td>
  <td class=xl66 width=139 style='width:104pt'>sigset_t __user *set</td>
  <td class=xl66 width=159 style='width:119pt'>size_t sigsetsize</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2171"
  target="_blank">kernel/signal.c:2171</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>177</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigtimedwait.2.html"
  target="_blank">sys_rt_sigtimedwait</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb1</td>
  <td class=xl66 width=139 style='width:104pt'>const sigset_t __user *uthese</td>
  <td class=xl66 width=159 style='width:119pt'>siginfo_t __user *uinfo</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">const struct timespec __user *uts</a></td>
  <td class=xl66 width=138 style='width:103pt'>size_t sigsetsize</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2242"
  target="_blank">kernel/signal.c:2242</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>178</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigqueueinfo.2.html"
  target="_blank">sys_rt_sigqueueinfo</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb2</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=159 style='width:119pt'>int sig</td>
  <td class=xl66 width=151 style='width:113pt'>siginfo_t __user *uinfo</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2404"
  target="_blank">kernel/signal.c:2404</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>179</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_sigsuspend.2.html"
  target="_blank">sys_rt_sigsuspend</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb3</td>
  <td class=xl66 width=139 style='width:104pt'>sigset_t __user *unewset</td>
  <td class=xl66 width=159 style='width:119pt'>size_t sigsetsize</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2710"
  target="_blank">kernel/signal.c:2710</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>180</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pread64.2.html"
  target="_blank">sys_pread64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb4</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>size_t count</td>
  <td class=xl66 width=138 style='width:103pt'>loff_t pos</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>181</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pwrite64.2.html"
  target="_blank">sys_pwrite64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>size_t count</td>
  <td class=xl66 width=138 style='width:103pt'>loff_t pos</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>182</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/chown16.2.html"
  target="_blank">sys_chown16</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>old_uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>old_gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/uid16.c?v=2.6.35#L19"
  target="_blank">kernel/uid16.c:19</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>183</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getcwd.2.html"
  target="_blank">sys_getcwd</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb7</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *buf</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long size</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/dcache.c?v=2.6.35#L2104"
  target="_blank">fs/dcache.c:2104</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>184</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/capget.2.html"
  target="_blank">sys_capget</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb8</td>
  <td class=xl66 width=139 style='width:104pt'>cap_user_header_t header</td>
  <td class=xl66 width=159 style='width:119pt'>cap_user_data_t dataptr</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/capability.c?v=2.6.35#L161"
  target="_blank">kernel/capability.c:161</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>185</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/capset.2.html"
  target="_blank">sys_capset</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xb9</td>
  <td class=xl66 width=139 style='width:104pt'>cap_user_header_t header</td>
  <td class=xl66 width=159 style='width:119pt'>const cap_user_data_t data</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/capability.c?v=2.6.35#L235"
  target="_blank">kernel/capability.c:235</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>186</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sigaltstack.2.html"
  target="_blank">sys_sigaltstack</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xba</td>
  <td class=xl66 width=139 style='width:104pt'>const stack_t __user *</td>
  <td class=xl66 width=159 style='width:119pt'>stack_t __user *</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/signal.c?v=2.6.35#L199"
  target="_blank">arch/alpha/kernel/signal.c:199</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>187</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sendfile.2.html"
  target="_blank">sys_sendfile</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xbb</td>
  <td class=xl66 width=139 style='width:104pt'>int out_fd</td>
  <td class=xl66 width=159 style='width:119pt'>int in_fd</td>
  <td class=xl66 width=151 style='width:113pt'>off_t __user *offset</td>
  <td class=xl66 width=138 style='width:103pt'>size_t count</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L897"
  target="_blank">fs/read_write.c:897</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>188</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xbc</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>189</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xbd</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>190</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/vfork.2.html"
  target="_blank">sys_vfork</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xbe</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/ptrace.h?v=2.6.35#L19"
  target="_blank">struct pt_regs *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/kernel/entry.S?v=2.6.35#L746"
  target="_blank">arch/alpha/kernel/entry.S:746</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>191</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getrlimit.2.html"
  target="_blank">sys_getrlimit</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xbf</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int resource</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L41"
  target="_blank">struct rlimit __user *rlim</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1237"
  target="_blank">kernel/sys.c:1237</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>192</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mmap_pgoff.2.html"
  target="_blank">sys_mmap_pgoff</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mmap.c?v=2.6.35#L1091"
  target="_blank">mm/mmap.c:1091</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>193</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/truncate64.2.html"
  target="_blank">sys_truncate64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc1</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t length</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>194</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ftruncate64.2.html"
  target="_blank">sys_ftruncate64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc2</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t length</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>195</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/stat64.2.html"
  target="_blank">sys_stat64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc3</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L25"
  target="_blank">struct stat64 __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L358"
  target="_blank">fs/stat.c:358</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>196</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lstat64.2.html"
  target="_blank">sys_lstat64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc4</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L25"
  target="_blank">struct stat64 __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L369"
  target="_blank">fs/stat.c:369</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>197</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fstat64.2.html"
  target="_blank">sys_fstat64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L25"
  target="_blank">struct stat64 __user *statbuf</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L380"
  target="_blank">fs/stat.c:380</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>198</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lchown.2.html"
  target="_blank">sys_lchown</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L583"
  target="_blank">fs/open.c:583</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>199</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getuid.2.html"
  target="_blank">sys_getuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc7</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1359"
  target="_blank">kernel/timer.c:1359</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>200</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getgid.2.html"
  target="_blank">sys_getgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc8</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1371"
  target="_blank">kernel/timer.c:1371</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>201</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/geteuid.2.html"
  target="_blank">sys_geteuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xc9</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1365"
  target="_blank">kernel/timer.c:1365</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>202</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getegid.2.html"
  target="_blank">sys_getegid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xca</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1377"
  target="_blank">kernel/timer.c:1377</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>203</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setreuid.2.html"
  target="_blank">sys_setreuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xcb</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t ruid</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t euid</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L594"
  target="_blank">kernel/sys.c:594</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>204</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setregid.2.html"
  target="_blank">sys_setregid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xcc</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t rgid</td>
  <td class=xl66 width=159 style='width:119pt'>gid_t egid</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L484"
  target="_blank">kernel/sys.c:484</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>205</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getgroups.2.html"
  target="_blank">sys_getgroups</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xcd</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=159 style='width:119pt'>gid_t __user *grouplist</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/groups.c?v=2.6.35#L203"
  target="_blank">kernel/groups.c:203</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>206</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setgroups.2.html"
  target="_blank">sys_setgroups</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xce</td>
  <td class=xl66 width=139 style='width:104pt'>int gidsetsize</td>
  <td class=xl66 width=159 style='width:119pt'>gid_t __user *grouplist</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/groups.c?v=2.6.35#L232"
  target="_blank">kernel/groups.c:232</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>207</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchown.2.html"
  target="_blank">sys_fchown</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xcf</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L602"
  target="_blank">fs/open.c:602</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>208</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setresuid.2.html"
  target="_blank">sys_setresuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd0</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t ruid</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t euid</td>
  <td class=xl66 width=151 style='width:113pt'>uid_t suid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L696"
  target="_blank">kernel/sys.c:696</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>209</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getresuid.2.html"
  target="_blank">sys_getresuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd1</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t __user *ruid</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t __user *euid</td>
  <td class=xl66 width=151 style='width:113pt'>uid_t __user *suid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L746"
  target="_blank">kernel/sys.c:746</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>210</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setresgid.2.html"
  target="_blank">sys_setresgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd2</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t rgid</td>
  <td class=xl66 width=159 style='width:119pt'>gid_t egid</td>
  <td class=xl66 width=151 style='width:113pt'>gid_t sgid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L761"
  target="_blank">kernel/sys.c:761</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>211</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getresgid.2.html"
  target="_blank">sys_getresgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd3</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t __user *rgid</td>
  <td class=xl66 width=159 style='width:119pt'>gid_t __user *egid</td>
  <td class=xl66 width=151 style='width:113pt'>gid_t __user *sgid</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L800"
  target="_blank">kernel/sys.c:800</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>212</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/chown.2.html"
  target="_blank">sys_chown</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd4</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *filename</td>
  <td class=xl66 width=159 style='width:119pt'>uid_t user</td>
  <td class=xl66 width=151 style='width:113pt'>gid_t group</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L539"
  target="_blank">fs/open.c:539</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>213</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setuid.2.html"
  target="_blank">sys_setuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd5</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t uid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L655"
  target="_blank">kernel/sys.c:655</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>214</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setgid.2.html"
  target="_blank">sys_setgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd6</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t gid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L531"
  target="_blank">kernel/sys.c:531</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>215</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setfsuid.2.html"
  target="_blank">sys_setfsuid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd7</td>
  <td class=xl66 width=139 style='width:104pt'>uid_t uid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L819"
  target="_blank">kernel/sys.c:819</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>216</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setfsgid.2.html"
  target="_blank">sys_setfsgid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd8</td>
  <td class=xl66 width=139 style='width:104pt'>gid_t gid</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L852"
  target="_blank">kernel/sys.c:852</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>217</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pivot_root.2.html"
  target="_blank">sys_pivot_root</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xd9</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *new_root</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *put_old</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namespace.c?v=2.6.35#L2184"
  target="_blank">fs/namespace.c:2184</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>218</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mincore.2.html"
  target="_blank">sys_mincore</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xda</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned char __user * vec</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mincore.c?v=2.6.35#L256"
  target="_blank">mm/mincore.c:256</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>219</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/madvise.2.html"
  target="_blank">sys_madvise</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xdb</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>int behavior</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/madvise.c?v=2.6.35#L335"
  target="_blank">mm/madvise.c:335</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>220</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getdents64.2.html"
  target="_blank">sys_getdents64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xdc</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/dirent.h?v=2.6.35#L4"
  target="_blank">struct linux_dirent64 __user *dirent</a></td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int count</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/readdir.c?v=2.6.35#L273"
  target="_blank">fs/readdir.c:273</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>221</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fcntl64.2.html"
  target="_blank">sys_fcntl64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xdd</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int cmd</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/fcntl.c?v=2.6.35#L452"
  target="_blank">fs/fcntl.c:452</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>222</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xde</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>223</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xdf</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>224</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/gettid.2.html"
  target="_blank">sys_gettid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/timer.c?v=2.6.35#L1493"
  target="_blank">kernel/timer.c:1493</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>225</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/readahead.2.html"
  target="_blank">sys_readahead</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe1</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=151 style='width:113pt'>size_t count</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>226</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/setxattr.2.html"
  target="_blank">sys_setxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe2</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>const void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>int flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L279"
  target="_blank">fs/xattr.c:279</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>227</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lsetxattr.2.html"
  target="_blank">sys_lsetxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe3</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>const void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>int flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L298"
  target="_blank">fs/xattr.c:298</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>228</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fsetxattr.2.html"
  target="_blank">sys_fsetxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe4</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>const void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>int flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L317"
  target="_blank">fs/xattr.c:317</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>229</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getxattr.2.html"
  target="_blank">sys_getxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe5</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L376"
  target="_blank">fs/xattr.c:376</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>230</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lgetxattr.2.html"
  target="_blank">sys_lgetxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe6</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L390"
  target="_blank">fs/xattr.c:390</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>231</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fgetxattr.2.html"
  target="_blank">sys_fgetxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe7</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>void __user *value</td>
  <td class=xl66 width=138 style='width:103pt'>size_t size</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L404"
  target="_blank">fs/xattr.c:404</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>232</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/listxattr.2.html"
  target="_blank">sys_listxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe8</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=151 style='width:113pt'>size_t size</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L449"
  target="_blank">fs/xattr.c:449</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>233</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/llistxattr.2.html"
  target="_blank">sys_llistxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xe9</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=151 style='width:113pt'>size_t size</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L463"
  target="_blank">fs/xattr.c:463</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>234</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/flistxattr.2.html"
  target="_blank">sys_flistxattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xea</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *list</td>
  <td class=xl66 width=151 style='width:113pt'>size_t size</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L477"
  target="_blank">fs/xattr.c:477</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>235</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/removexattr.2.html"
  target="_blank">sys_removexattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xeb</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L509"
  target="_blank">fs/xattr.c:509</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>236</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lremovexattr.2.html"
  target="_blank">sys_lremovexattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xec</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L527"
  target="_blank">fs/xattr.c:527</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>237</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fremovexattr.2.html"
  target="_blank">sys_fremovexattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xed</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *name</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/xattr.c?v=2.6.35#L545"
  target="_blank">fs/xattr.c:545</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>238</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/tkill.2.html"
  target="_blank">sys_tkill</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xee</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl66 width=159 style='width:119pt'>int sig</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2395"
  target="_blank">kernel/signal.c:2395</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>239</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sendfile64.2.html"
  target="_blank">sys_sendfile64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xef</td>
  <td class=xl66 width=139 style='width:104pt'>int out_fd</td>
  <td class=xl66 width=159 style='width:119pt'>int in_fd</td>
  <td class=xl66 width=151 style='width:113pt'>loff_t __user *offset</td>
  <td class=xl66 width=138 style='width:103pt'>size_t count</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L916"
  target="_blank">fs/read_write.c:916</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>240</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/futex.2.html"
  target="_blank">sys_futex</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf0</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/futex.c?v=2.6.35#L2605"
  target="_blank">kernel/futex.c:2605</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>241</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_setaffinity.2.html"
  target="_blank">sys_sched_setaffinity</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf1</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int len</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long __user
  *user_mask_ptr</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4765"
  target="_blank">kernel/sched.c:4765</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>242</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sched_getaffinity.2.html"
  target="_blank">sys_sched_getaffinity</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf2</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int len</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long __user
  *user_mask_ptr</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sched.c?v=2.6.35#L4817"
  target="_blank">kernel/sched.c:4817</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>243</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/set_thread_area.2.html"
  target="_blank">sys_set_thread_area</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf3</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/x86/include/asm/ldt.h?v=2.6.35#L20"
  target="_blank">struct user_desc __user *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/kernel/syscall.c?v=2.6.35#L222"
  target="_blank">arch/mips/kernel/syscall.c:222</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>244</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/get_thread_area.2.html"
  target="_blank">sys_get_thread_area</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf4</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/arch/x86/include/asm/ldt.h?v=2.6.35#L20"
  target="_blank">struct user_desc __user *</a></td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>245</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/io_setup.2.html"
  target="_blank">sys_io_setup</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf5</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned nr_reqs</td>
  <td class=xl66 width=159 style='width:119pt'>aio_context_t __user *ctx</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/aio.c?v=2.6.35#L1245"
  target="_blank">fs/aio.c:1245</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>246</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/io_destroy.2.html"
  target="_blank">sys_io_destroy</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf6</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/aio.c?v=2.6.35#L1283"
  target="_blank">fs/aio.c:1283</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>247</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/io_getevents.2.html"
  target="_blank">sys_io_getevents</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf7</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx_id</td>
  <td class=xl66 width=159 style='width:119pt'>long min_nr</td>
  <td class=xl66 width=151 style='width:113pt'>long nr</td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/aio_abi.h?v=2.6.35#L58"
  target="_blank">struct io_event __user *events</a></td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *timeout</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/aio.c?v=2.6.35#L1808"
  target="_blank">fs/aio.c:1808</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>248</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/io_submit.2.html"
  target="_blank">sys_io_submit</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf8</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t</td>
  <td class=xl66 width=159 style='width:119pt'>long</td>
  <td class=xl66 width=151 style='width:113pt'>struct iocb __user * __user *</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/aio.c?v=2.6.35#L1711"
  target="_blank">fs/aio.c:1711</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>249</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/io_cancel.2.html"
  target="_blank">sys_io_cancel</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xf9</td>
  <td class=xl66 width=139 style='width:104pt'>aio_context_t ctx_id</td>
  <td class=xl66 width=159 style='width:119pt'>struct iocb __user *iocb</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/aio_abi.h?v=2.6.35#L58"
  target="_blank">struct io_event __user *result</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/aio.c?v=2.6.35#L1746"
  target="_blank">fs/aio.c:1746</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>250</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fadvise64.2.html"
  target="_blank">sys_fadvise64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xfa</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=151 style='width:113pt'>size_t len</td>
  <td class=xl66 width=138 style='width:103pt'>int advice</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>251</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0xfb</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>252</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/exit_group.2.html"
  target="_blank">sys_exit_group</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xfc</td>
  <td class=xl66 width=139 style='width:104pt'>int error_code</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exit.c?v=2.6.35#L1087"
  target="_blank">kernel/exit.c:1087</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>253</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/lookup_dcookie.2.html"
  target="_blank">sys_lookup_dcookie</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xfd</td>
  <td class=xl66 width=139 style='width:104pt'>u64 cookie64</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *buf</td>
  <td class=xl66 width=151 style='width:113pt'>size_t len</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>254</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/epoll_create.2.html"
  target="_blank">sys_epoll_create</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xfe</td>
  <td class=xl66 width=139 style='width:104pt'>int size</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventpoll.c?v=2.6.35#L1215"
  target="_blank">fs/eventpoll.c:1215</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>255</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/epoll_ctl.2.html"
  target="_blank">sys_epoll_ctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0xff</td>
  <td class=xl66 width=139 style='width:104pt'>int epfd</td>
  <td class=xl66 width=159 style='width:119pt'>int op</td>
  <td class=xl66 width=151 style='width:113pt'>int fd</td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/eventpoll.h?v=2.6.35#L47"
  target="_blank">struct epoll_event __user *event</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventpoll.c?v=2.6.35#L1228"
  target="_blank">fs/eventpoll.c:1228</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>256</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/epoll_wait.2.html"
  target="_blank">sys_epoll_wait</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x100</td>
  <td class=xl66 width=139 style='width:104pt'>int epfd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/eventpoll.h?v=2.6.35#L47"
  target="_blank">struct epoll_event __user *events</a></td>
  <td class=xl66 width=151 style='width:113pt'>int maxevents</td>
  <td class=xl66 width=138 style='width:103pt'>int timeout</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventpoll.c?v=2.6.35#L1320"
  target="_blank">fs/eventpoll.c:1320</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>257</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/remap_file_pages.2.html"
  target="_blank">sys_remap_file_pages</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x101</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long start</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long size</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long prot</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long pgoff</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/fremap.c?v=2.6.35#L123"
  target="_blank">mm/fremap.c:123</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>258</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/set_tid_address.2.html"
  target="_blank">sys_set_tid_address</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x102</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *tidptr</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/fork.c?v=2.6.35#L920"
  target="_blank">kernel/fork.c:920</a></td>
 </tr>
 <tr height=96 style='height:72.0pt'>
  <td height=96 class=xl66 align=right width=83 style='height:72.0pt;
  width:62pt'>259</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timer_create.2.html"
  target="_blank">sys_timer_create</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x103</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/asm-generic/siginfo.h?v=2.6.35#L259"
  target="_blank">struct sigevent __user *timer_event_spec</a></td>
  <td class=xl66 width=151 style='width:113pt'>timer_t __user *
  created_timer_id</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L522"
  target="_blank">kernel/posix-timers.c:522</a></td>
 </tr>
 <tr height=96 style='height:72.0pt'>
  <td height=96 class=xl66 align=right width=83 style='height:72.0pt;
  width:62pt'>260</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timer_settime.2.html"
  target="_blank">sys_timer_settime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x104</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">const struct itimerspec __user *new_setting</a></td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">struct itimerspec __user *old_setting</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L800"
  target="_blank">kernel/posix-timers.c:800</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>261</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timer_gettime.2.html"
  target="_blank">sys_timer_gettime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x105</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">struct itimerspec __user *setting</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L702"
  target="_blank">kernel/posix-timers.c:702</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>262</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timer_getoverrun.2.html"
  target="_blank">sys_timer_getoverrun</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x106</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L732"
  target="_blank">kernel/posix-timers.c:732</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>263</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timer_delete.2.html"
  target="_blank">sys_timer_delete</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x107</td>
  <td class=xl66 width=139 style='width:104pt'>timer_t timer_id</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L855"
  target="_blank">kernel/posix-timers.c:855</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>264</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/clock_settime.2.html"
  target="_blank">sys_clock_settime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x108</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">const struct timespec __user *tp</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L941"
  target="_blank">kernel/posix-timers.c:941</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>265</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/clock_gettime.2.html"
  target="_blank">sys_clock_gettime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x109</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *tp</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L954"
  target="_blank">kernel/posix-timers.c:954</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>266</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/clock_getres.2.html"
  target="_blank">sys_clock_getres</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10a</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *tp</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L971"
  target="_blank">kernel/posix-timers.c:971</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>267</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/clock_nanosleep.2.html"
  target="_blank">sys_clock_nanosleep</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10b</td>
  <td class=xl66 width=139 style='width:104pt'>clockid_t which_clock</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">const struct timespec __user *rqtp</a></td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *rmtp</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/posix-timers.c?v=2.6.35#L1001"
  target="_blank">kernel/posix-timers.c:1001</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>268</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/statfs64.2.html"
  target="_blank">sys_statfs64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10c</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *path</td>
  <td class=xl66 width=159 style='width:119pt'>size_t sz</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/include/asm/statfs.h?v=2.6.35#L63"
  target="_blank">struct statfs64 __user *buf</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/statfs.c?v=2.6.35#L118"
  target="_blank">fs/statfs.c:118</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>269</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fstatfs64.2.html"
  target="_blank">sys_fstatfs64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int fd</td>
  <td class=xl66 width=159 style='width:119pt'>size_t sz</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/mips/include/asm/statfs.h?v=2.6.35#L63"
  target="_blank">struct statfs64 __user *buf</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/statfs.c?v=2.6.35#L154"
  target="_blank">fs/statfs.c:154</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>270</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/tgkill.2.html"
  target="_blank">sys_tgkill</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10e</td>
  <td class=xl66 width=139 style='width:104pt'>int tgid</td>
  <td class=xl66 width=159 style='width:119pt'>int pid</td>
  <td class=xl66 width=151 style='width:113pt'>int sig</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2383"
  target="_blank">kernel/signal.c:2383</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>271</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/utimes.2.html"
  target="_blank">sys_utimes</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x10f</td>
  <td class=xl66 width=139 style='width:104pt'>char __user *filename</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L20"
  target="_blank">struct timeval __user *utimes</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/utimes.c?v=2.6.35#L219"
  target="_blank">fs/utimes.c:219</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>272</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fadvise64_64.2.html"
  target="_blank">sys_fadvise64_64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x110</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=151 style='width:113pt'>loff_t len</td>
  <td class=xl66 width=138 style='width:103pt'>int advice</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>273</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x111</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>274</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mbind.2.html"
  target="_blank">sys_mbind</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x112</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mempolicy.c?v=2.6.35#L1232"
  target="_blank">mm/mempolicy.c:1232</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>275</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/get_mempolicy.2.html"
  target="_blank">sys_get_mempolicy</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x113</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *policy</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long __user *nmask</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long maxnode</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long addr</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mempolicy.c?v=2.6.35#L1348"
  target="_blank">mm/mempolicy.c:1348</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>276</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/set_mempolicy.2.html"
  target="_blank">sys_set_mempolicy</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x114</td>
  <td class=xl66 width=139 style='width:104pt'>int mode</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long __user *nmask</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long maxnode</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mempolicy.c?v=2.6.35#L1254"
  target="_blank">mm/mempolicy.c:1254</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>277</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_open.2.html"
  target="_blank">sys_mq_open</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x115</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>int oflag</td>
  <td class=xl66 width=151 style='width:113pt'>mode_t mode</td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/mqueue.h?v=2.6.35#L25"
  target="_blank">struct mq_attr __user *attr</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L673"
  target="_blank">ipc/mqueue.c:673</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>278</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_unlink.2.html"
  target="_blank">sys_mq_unlink</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x116</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *name</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L746"
  target="_blank">ipc/mqueue.c:746</a></td>
 </tr>
 <tr height=96 style='height:72.0pt'>
  <td height=96 class=xl66 align=right width=83 style='height:72.0pt;
  width:62pt'>279</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_timedsend.2.html"
  target="_blank">sys_mq_timedsend</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x117</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *msg_ptr</td>
  <td class=xl66 width=151 style='width:113pt'>size_t msg_len</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned int msg_prio</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">const struct timespec __user *abs_timeout</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L840"
  target="_blank">ipc/mqueue.c:840</a></td>
 </tr>
 <tr height=96 style='height:72.0pt'>
  <td height=96 class=xl66 align=right width=83 style='height:72.0pt;
  width:62pt'>280</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_timedreceive.2.html"
  target="_blank">sys_mq_timedreceive</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x118</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *msg_ptr</td>
  <td class=xl66 width=151 style='width:113pt'>size_t msg_len</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned int __user *msg_prio</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">const struct timespec __user *abs_timeout</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L934"
  target="_blank">ipc/mqueue.c:934</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>281</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_notify.2.html"
  target="_blank">sys_mq_notify</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x119</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/asm-generic/siginfo.h?v=2.6.35#L259"
  target="_blank">const struct sigevent __user *notification</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L1023"
  target="_blank">ipc/mqueue.c:1023</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>282</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mq_getsetattr.2.html"
  target="_blank">sys_mq_getsetattr</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x11a</td>
  <td class=xl66 width=139 style='width:104pt'>mqd_t mqdes</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/mqueue.h?v=2.6.35#L25"
  target="_blank">const struct mq_attr __user *mqstat</a></td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/mqueue.h?v=2.6.35#L25"
  target="_blank">struct mq_attr __user *omqstat</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/ipc/mqueue.c?v=2.6.35#L1154"
  target="_blank">ipc/mqueue.c:1154</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>283</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/kexec_load.2.html"
  target="_blank">sys_kexec_load</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x11b</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long entry</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long nr_segments</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/kexec.h?v=2.6.35#L61"
  target="_blank">struct kexec_segment __user *segments</a></td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/kexec.c?v=2.6.35#L939"
  target="_blank">kernel/kexec.c:939</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>284</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/waitid.2.html"
  target="_blank">sys_waitid</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x11c</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=159 style='width:119pt'>pid_t pid</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/ia64/include/asm/siginfo.h?v=2.6.35#L19"
  target="_blank">struct siginfo __user *infop</a></td>
  <td class=xl66 width=138 style='width:103pt'>int options</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/resource.h?v=2.6.35#L22"
  target="_blank">struct rusage __user *ru</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/exit.c?v=2.6.35#L1655"
  target="_blank">kernel/exit.c:1655</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>285</td>
  <td class=xl66 width=83 style='width:62pt'>not implemented</td>
  <td class=xl66 width=83 style='width:62pt'>0x11d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl66 width=154 style='width:116pt'></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>286</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/add_key.2.html"
  target="_blank">sys_add_key</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x11e</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *_type</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *_description</td>
  <td class=xl66 width=151 style='width:113pt'>const void __user *_payload</td>
  <td class=xl66 width=138 style='width:103pt'>size_t plen</td>
  <td class=xl66 width=127 style='width:95pt'>key_serial_t destringid</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/security/keys/keyctl.c?v=2.6.35#L57"
  target="_blank">security/keys/keyctl.c:57</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>287</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/request_key.2.html"
  target="_blank">sys_request_key</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x11f</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user *_type</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *_description</td>
  <td class=xl66 width=151 style='width:113pt'>const char __user *_callout_info</td>
  <td class=xl66 width=138 style='width:103pt'>key_serial_t destringid</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/security/keys/keyctl.c?v=2.6.35#L149"
  target="_blank">security/keys/keyctl.c:149</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>288</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/keyctl.2.html"
  target="_blank">sys_keyctl</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x120</td>
  <td class=xl66 width=139 style='width:104pt'>int cmd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long arg2</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long arg3</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long arg4</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long arg5</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/security/keys/keyctl.c?v=2.6.35#L1338"
  target="_blank">security/keys/keyctl.c:1338</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>289</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ioprio_set.2.html"
  target="_blank">sys_ioprio_set</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x121</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=159 style='width:119pt'>int who</td>
  <td class=xl66 width=151 style='width:113pt'>int ioprio</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/ioprio.c?v=2.6.35#L76"
  target="_blank">fs/ioprio.c:76</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>290</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ioprio_get.2.html"
  target="_blank">sys_ioprio_get</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x122</td>
  <td class=xl66 width=139 style='width:104pt'>int which</td>
  <td class=xl66 width=159 style='width:119pt'>int who</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/ioprio.c?v=2.6.35#L192"
  target="_blank">fs/ioprio.c:192</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>291</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/inotify_init.2.html"
  target="_blank">sys_inotify_init</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x123</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/notify/inotify/inotify_user.c?v=2.6.35#L680"
  target="_blank">fs/notify/inotify/inotify_user.c:680</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>292</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/inotify_add_watch.2.html"
  target="_blank">sys_inotify_add_watch</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x124</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *path</td>
  <td class=xl66 width=151 style='width:113pt'>u32 mask</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/notify/inotify/inotify_user.c?v=2.6.35#L685"
  target="_blank">fs/notify/inotify/inotify_user.c:685</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>293</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/inotify_rm_watch.2.html"
  target="_blank">sys_inotify_rm_watch</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x125</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>__s32 wd</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/notify/inotify/inotify_user.c?v=2.6.35#L726"
  target="_blank">fs/notify/inotify/inotify_user.c:726</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>294</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/migrate_pages.2.html"
  target="_blank">sys_migrate_pages</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x126</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t pid</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned long maxnode</td>
  <td class=xl66 width=151 style='width:113pt'>const unsigned long __user *from</td>
  <td class=xl66 width=138 style='width:103pt'>const unsigned long __user *to</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/mempolicy.c?v=2.6.35#L1273"
  target="_blank">mm/mempolicy.c:1273</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>295</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/openat.2.html"
  target="_blank">sys_openat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x127</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=151 style='width:113pt'>int flags</td>
  <td class=xl66 width=138 style='width:103pt'>int mode</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L913"
  target="_blank">fs/open.c:913</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>296</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mkdirat.2.html"
  target="_blank">sys_mkdirat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x128</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user * pathname</td>
  <td class=xl66 width=151 style='width:113pt'>int mode</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2093"
  target="_blank">fs/namei.c:2093</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>297</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/mknodat.2.html"
  target="_blank">sys_mknodat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x129</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user * filename</td>
  <td class=xl66 width=151 style='width:113pt'>int mode</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned dev</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2012"
  target="_blank">fs/namei.c:2012</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>298</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchownat.2.html"
  target="_blank">sys_fchownat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12a</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=151 style='width:113pt'>uid_t user</td>
  <td class=xl66 width=138 style='width:103pt'>gid_t group</td>
  <td class=xl66 width=127 style='width:95pt'>int flag</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L558"
  target="_blank">fs/open.c:558</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>299</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/futimesat.2.html"
  target="_blank">sys_futimesat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12b</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *filename</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L20"
  target="_blank">struct timeval __user *utimes</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/utimes.c?v=2.6.35#L191"
  target="_blank">fs/utimes.c:191</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>300</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fstatat64.2.html"
  target="_blank">sys_fstatat64</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12c</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *filename</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/arch/alpha/include/asm/stat.h?v=2.6.35#L25"
  target="_blank">struct stat64 __user *statbuf</a></td>
  <td class=xl66 width=138 style='width:103pt'>int flag</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L391"
  target="_blank">fs/stat.c:391</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>301</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/unlinkat.2.html"
  target="_blank">sys_unlinkat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12d</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user * pathname</td>
  <td class=xl66 width=151 style='width:113pt'>int flag</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2341"
  target="_blank">fs/namei.c:2341</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>302</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/renameat.2.html"
  target="_blank">sys_renameat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12e</td>
  <td class=xl66 width=139 style='width:104pt'>int olddfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user * oldname</td>
  <td class=xl66 width=151 style='width:113pt'>int newdfd</td>
  <td class=xl66 width=138 style='width:103pt'>const char __user * newname</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2671"
  target="_blank">fs/namei.c:2671</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>303</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/linkat.2.html"
  target="_blank">sys_linkat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x12f</td>
  <td class=xl66 width=139 style='width:104pt'>int olddfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *oldname</td>
  <td class=xl66 width=151 style='width:113pt'>int newdfd</td>
  <td class=xl66 width=138 style='width:103pt'>const char __user *newname</td>
  <td class=xl66 width=127 style='width:95pt'>int flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2470"
  target="_blank">fs/namei.c:2470</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>304</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/symlinkat.2.html"
  target="_blank">sys_symlinkat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x130</td>
  <td class=xl66 width=139 style='width:104pt'>const char __user * oldname</td>
  <td class=xl66 width=159 style='width:119pt'>int newdfd</td>
  <td class=xl66 width=151 style='width:113pt'>const char __user * newname</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/namei.c?v=2.6.35#L2377"
  target="_blank">fs/namei.c:2377</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>305</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/readlinkat.2.html"
  target="_blank">sys_readlinkat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x131</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *path</td>
  <td class=xl66 width=151 style='width:113pt'>char __user *buf</td>
  <td class=xl66 width=138 style='width:103pt'>int bufsiz</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/stat.c?v=2.6.35#L284"
  target="_blank">fs/stat.c:284</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>306</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fchmodat.2.html"
  target="_blank">sys_fchmodat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x132</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user * filename</td>
  <td class=xl66 width=151 style='width:113pt'>mode_t mode</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L474"
  target="_blank">fs/open.c:474</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>307</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/faccessat.2.html"
  target="_blank">sys_faccessat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x133</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>const char __user *filename</td>
  <td class=xl66 width=151 style='width:113pt'>int mode</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/open.c?v=2.6.35#L286"
  target="_blank">fs/open.c:286</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>308</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pselect6.2.html"
  target="_blank">sys_pselect6</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x134</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L675"
  target="_blank">fs/select.c:675</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>309</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/ppoll.2.html"
  target="_blank">sys_ppoll</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x135</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/asm-generic/poll.h?v=2.6.35#L31"
  target="_blank">struct pollfd __user *ufds</a></td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int nfds</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *tsp</a></td>
  <td class=xl66 width=138 style='width:103pt'>const sigset_t __user *sigmask</td>
  <td class=xl66 width=127 style='width:95pt'>size_t sigsetsize</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/select.c?v=2.6.35#L950"
  target="_blank">fs/select.c:950</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>310</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/unshare.2.html"
  target="_blank">sys_unshare</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x136</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long unshare_flags</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/fork.c?v=2.6.35#L1624"
  target="_blank">kernel/fork.c:1624</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>311</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/set_robust_list.2.html"
  target="_blank">sys_set_robust_list</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x137</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/futex.h?v=2.6.35#L69"
  target="_blank">struct robust_list_head __user *head</a></td>
  <td class=xl66 width=159 style='width:119pt'>size_t len</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/futex.c?v=2.6.35#L2351"
  target="_blank">kernel/futex.c:2351</a></td>
 </tr>
 <tr height=96 style='height:72.0pt'>
  <td height=96 class=xl66 align=right width=83 style='height:72.0pt;
  width:62pt'>312</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/get_robust_list.2.html"
  target="_blank">sys_get_robust_list</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x138</td>
  <td class=xl66 width=139 style='width:104pt'>int pid</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/futex.h?v=2.6.35#L69"
  target="_blank">struct robust_list_head __user * __user *head_ptr</a></td>
  <td class=xl66 width=151 style='width:113pt'>size_t __user *len_ptr</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/futex.c?v=2.6.35#L2373"
  target="_blank">kernel/futex.c:2373</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>313</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/splice.2.html"
  target="_blank">sys_splice</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x139</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/splice.c?v=2.6.35#L1718"
  target="_blank">fs/splice.c:1718</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>314</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/sync_file_range.2.html"
  target="_blank">sys_sync_file_range</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13a</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>loff_t offset</td>
  <td class=xl66 width=151 style='width:113pt'>loff_t nbytes</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned int flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>315</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/tee.2.html"
  target="_blank">sys_tee</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13b</td>
  <td class=xl66 width=139 style='width:104pt'>int fdin</td>
  <td class=xl66 width=159 style='width:119pt'>int fdout</td>
  <td class=xl66 width=151 style='width:113pt'>size_t len</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned int flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/splice.c?v=2.6.35#L2061"
  target="_blank">fs/splice.c:2061</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>316</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/vmsplice.2.html"
  target="_blank">sys_vmsplice</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13c</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>const struct iovec __user *iov</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long nr_segs</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned int flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/splice.c?v=2.6.35#L1692"
  target="_blank">fs/splice.c:1692</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>317</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/move_pages.2.html"
  target="_blank">sys_move_pages</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13d</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/mm/migrate.c?v=2.6.35#L1075"
  target="_blank">mm/migrate.c:1075</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>318</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/getcpu.2.html"
  target="_blank">sys_getcpu</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned __user *cpu</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned __user *node</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/getcpu.h?v=2.6.35#L14"
  target="_blank">struct getcpu_cache __user *cache</a></td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/sys.c?v=2.6.35#L1621"
  target="_blank">kernel/sys.c:1621</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>319</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/epoll_pwait.2.html"
  target="_blank">sys_epoll_pwait</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x13f</td>
  <td class=xl66 width=139 style='width:104pt'>-</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventpoll.c?v=2.6.35#L1373"
  target="_blank">fs/eventpoll.c:1373</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>320</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/utimensat.2.html"
  target="_blank">sys_utimensat</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x140</td>
  <td class=xl66 width=139 style='width:104pt'>int dfd</td>
  <td class=xl66 width=159 style='width:119pt'>char __user *filename</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *utimes</a></td>
  <td class=xl66 width=138 style='width:103pt'>int flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/utimes.c?v=2.6.35#L173"
  target="_blank">fs/utimes.c:173</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>321</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/signalfd.2.html"
  target="_blank">sys_signalfd</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x141</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=159 style='width:119pt'>sigset_t __user *user_mask</td>
  <td class=xl66 width=151 style='width:113pt'>size_t sizemask</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/signalfd.c?v=2.6.35#L265"
  target="_blank">fs/signalfd.c:265</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>322</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timerfd_create.2.html"
  target="_blank">sys_timerfd_create</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x142</td>
  <td class=xl66 width=139 style='width:104pt'>int clockid</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/timerfd.c?v=2.6.35#L164"
  target="_blank">fs/timerfd.c:164</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>323</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/eventfd.2.html"
  target="_blank">sys_eventfd</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x143</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int count</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventfd.c?v=2.6.35#L434"
  target="_blank">fs/eventfd.c:434</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>324</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/fallocate.2.html"
  target="_blank">sys_fallocate</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x144</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl66 width=159 style='width:119pt'>int mode</td>
  <td class=xl66 width=151 style='width:113pt'>loff_t offset</td>
  <td class=xl66 width=138 style='width:103pt'>loff_t len</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/not%20found?v=2.6.35#L"
  target="_blank">not found:</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>325</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timerfd_settime.2.html"
  target="_blank">sys_timerfd_settime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x145</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl67 width=151 style='width:113pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">const struct itimerspec __user *utmr</a></td>
  <td class=xl67 width=138 style='width:103pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">struct itimerspec __user *otmr</a></td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/timerfd.c?v=2.6.35#L194"
  target="_blank">fs/timerfd.c:194</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>326</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/timerfd_gettime.2.html"
  target="_blank">sys_timerfd_gettime</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x146</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/time.h?v=2.6.35#L258"
  target="_blank">struct itimerspec __user *otmr</a></td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/timerfd.c?v=2.6.35#L252"
  target="_blank">fs/timerfd.c:252</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>327</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/signalfd4.2.html"
  target="_blank">sys_signalfd4</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x147</td>
  <td class=xl66 width=139 style='width:104pt'>int ufd</td>
  <td class=xl66 width=159 style='width:119pt'>sigset_t __user *user_mask</td>
  <td class=xl66 width=151 style='width:113pt'>size_t sizemask</td>
  <td class=xl66 width=138 style='width:103pt'>int flags</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/signalfd.c?v=2.6.35#L211"
  target="_blank">fs/signalfd.c:211</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>328</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/eventfd2.2.html"
  target="_blank">sys_eventfd2</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x148</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int count</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventfd.c?v=2.6.35#L409"
  target="_blank">fs/eventfd.c:409</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>329</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/epoll_create1.2.html"
  target="_blank">sys_epoll_create1</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x149</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/eventpoll.c?v=2.6.35#L1187"
  target="_blank">fs/eventpoll.c:1187</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>330</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/dup3.2.html"
  target="_blank">sys_dup3</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14a</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned int oldfd</td>
  <td class=xl66 width=159 style='width:119pt'>unsigned int newfd</td>
  <td class=xl66 width=151 style='width:113pt'>int flags</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/fcntl.c?v=2.6.35#L53"
  target="_blank">fs/fcntl.c:53</a></td>
 </tr>
 <tr height=38 style='height:28.8pt'>
  <td height=38 class=xl66 align=right width=83 style='height:28.8pt;
  width:62pt'>331</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pipe2.2.html"
  target="_blank">sys_pipe2</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14b</td>
  <td class=xl66 width=139 style='width:104pt'>int __user *fildes</td>
  <td class=xl66 width=159 style='width:119pt'>int flags</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/pipe.c?v=2.6.35#L1101"
  target="_blank">fs/pipe.c:1101</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>332</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/inotify_init1.2.html"
  target="_blank">sys_inotify_init1</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14c</td>
  <td class=xl66 width=139 style='width:104pt'>int flags</td>
  <td class=xl66 width=159 style='width:119pt'>-</td>
  <td class=xl66 width=151 style='width:113pt'>-</td>
  <td class=xl66 width=138 style='width:103pt'>-</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/notify/inotify/inotify_user.c?v=2.6.35#L640"
  target="_blank">fs/notify/inotify/inotify_user.c:640</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>333</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/preadv.2.html"
  target="_blank">sys_preadv</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14d</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=159 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long vlen</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long pos_l</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long pos_h</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L759"
  target="_blank">fs/read_write.c:759</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>334</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/pwritev.2.html"
  target="_blank">sys_pwritev</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14e</td>
  <td class=xl66 width=139 style='width:104pt'>unsigned long fd</td>
  <td class=xl66 width=159 style='width:119pt'>const struct iovec __user *vec</td>
  <td class=xl66 width=151 style='width:113pt'>unsigned long vlen</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned long pos_l</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long pos_h</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/fs/read_write.c?v=2.6.35#L784"
  target="_blank">fs/read_write.c:784</a></td>
 </tr>
 <tr height=58 style='height:43.2pt'>
  <td height=58 class=xl66 align=right width=83 style='height:43.2pt;
  width:62pt'>335</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/rt_tgsigqueueinfo.2.html"
  target="_blank">sys_rt_tgsigqueueinfo</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x14f</td>
  <td class=xl66 width=139 style='width:104pt'>pid_t tgid</td>
  <td class=xl66 width=159 style='width:119pt'>pid_t pid</td>
  <td class=xl66 width=151 style='width:113pt'>int sig</td>
  <td class=xl66 width=138 style='width:103pt'>siginfo_t __user *uinfo</td>
  <td class=xl66 width=127 style='width:95pt'>-</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/signal.c?v=2.6.35#L2437"
  target="_blank">kernel/signal.c:2437</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>336</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/perf_event_open.2.html"
  target="_blank">sys_perf_event_open</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x150</td>
  <td class=xl67 width=139 style='width:104pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/perf_event.h?v=2.6.35#L166"
  target="_blank">struct perf_event_attr __user *attr_uptr</a></td>
  <td class=xl66 width=159 style='width:119pt'>pid_t pid</td>
  <td class=xl66 width=151 style='width:113pt'>int cpu</td>
  <td class=xl66 width=138 style='width:103pt'>int group_fd</td>
  <td class=xl66 width=127 style='width:95pt'>unsigned long flags</td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/kernel/perf_event.c?v=2.6.35#L5065"
  target="_blank">kernel/perf_event.c:5065</a></td>
 </tr>
 <tr height=77 style='height:57.6pt'>
  <td height=77 class=xl66 align=right width=83 style='height:57.6pt;
  width:62pt'>337</td>
  <td class=xl67 width=83 style='width:62pt'><a
  href="http://www.kernel.org/doc/man-pages/online/pages/man2/recvmmsg.2.html"
  target="_blank">sys_recvmmsg</a></td>
  <td class=xl66 width=83 style='width:62pt'>0x151</td>
  <td class=xl66 width=139 style='width:104pt'>int fd</td>
  <td class=xl67 width=159 style='width:119pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/socket.h?v=2.6.35#L72"
  target="_blank">struct mmsghdr __user *msg</a></td>
  <td class=xl66 width=151 style='width:113pt'>unsigned int vlen</td>
  <td class=xl66 width=138 style='width:103pt'>unsigned flags</td>
  <td class=xl67 width=127 style='width:95pt'><a
  href="http://lxr.free-electrons.com/source/include/linux/coda.h?v=2.6.35#L116"
  target="_blank">struct timespec __user *timeout</a></td>
  <td class=xl67 width=154 style='width:116pt'><a
  href="http://lxr.free-electrons.com/source/net/socket.c?v=2.6.35#L2168"
  target="_blank">net/socket.c:2168</a></td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=83 style='width:62pt'></td>
  <td width=83 style='width:62pt'></td>
  <td width=83 style='width:62pt'></td>
  <td width=139 style='width:104pt'></td>
  <td width=159 style='width:119pt'></td>
  <td width=151 style='width:113pt'></td>
  <td width=138 style='width:103pt'></td>
  <td width=127 style='width:95pt'></td>
  <td width=154 style='width:116pt'></td>
 </tr>
 <![endif]>
</table>

</body>

</html>
