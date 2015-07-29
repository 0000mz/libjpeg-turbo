Independent JPEG Group's JPEG software release 6b
  with x86 SIMD extension for IJG JPEG library version 1.02
    == README ==
-----------------------------------------------------------

    ** Note **
The accompanying documents related to x86 SIMD extension are written in
Japanese. The English version of these documents is currently unavailable.
I apologize for this inconvenience to international programmers.

Most of the source code of the extension part is written in assembly
language. To compile the source, you need NASM (netwide assembler).
NASM is available from http://nasm.sourceforge.net/ or
http://sourceforge.net/project/showfiles.php?group_id=6208 .

At present, the x86 SIMD extension doesn't support 64-bit mode of
AMD64 (x86_64).

The x86 SIMD extension is an unofficial extension to the IJG JPEG
software. Please do not send any questions about this distribution
to the Independent JPEG Group.

For conditions of distribution and use, see the IJG's README file.
The same conditions apply to this SIMD-extended JPEG software.



�����Υ��եȤ�

  JPEG �Υ��ݡ��ȥ饤�֥��Ȥ��ƹ����Ȥ��Ƥ��� Independent JPEG Group's
  JPEG library (libjpeg �饤�֥��) �ˡ�Intel x86 �� CPU �λ��� SIMD ̿���
  ���Ѥ���������(�롼����)�򿷤����ɲä�����®����¤������ΤǤ���
  MMX �� SSE �ʤɤ� SIMD �黻��ǽ���������Ƥ���ץ��å����ư�����ȡ�
  ���ꥸ�ʥ��Ǥ� libjpeg �饤�֥�����Ӥ��� 2��3 �����٤�®�٤�ư��ޤ���
  �ޤ���SIMD ���˰ͤ�ʤ���®����¤�⤤���Ĥ��ܤ���Ƥ��ꡢSIMD �黻�λȤ�
  �ʤ��췿CPU�ˤ����Ƥ⡢���ꥸ�ʥ��Ǥ���Ӥ��ƽ��������ٹ�®��ư��ޤ���

  JPEG ���̡�Ÿ�������ι�®������Ū�Ȥ��Ƥ��ޤ�����ư��®�ٺ�ͥ��ǤϤʤ���
  ���ꥸ�ʥ��Ǥ�Ʊ���ʾ�η׻����٤���Ĥ��Ȥ��ͥ��˹ͤ��������ɤ����
  ���Ƥ��ޤ����ºݡ�DCT�黻����ư������DCT��Ȥä���硢����ӡ�����ü��
  ����ץ����(h1v2)�����JPEG�ե������Ÿ�������������Ƥϡ�
  ���ꥸ�ʥ��Ǥȣ��ӥåȤ���ʤ���̤�Ф��ޤ����嵭�Σ��Ĥ��㳰�ξ���
  ���ꥸ�ʥ��Ǥ��Ϲ�����(�����ٲ�)����Ƥ��ޤ���

  SIMD �б����˺ݤ��Ƥϡ���ǽ�ʸ¤ꡢ���ꥸ�ʥ��Ǥ� libjpeg �饤�֥��Ȥ�
  �ߴ����������ʤ��褦�˹�θ����Ƥ��ޤ��Τǡ��ۤȤ�ɤξ�硢���ꥸ�ʥ�
  �Ǥ򤽤Τޤ��֤������뤳�Ȥ���ǽ�Ǥ����äˡ���ͭ�饤�֥��˴ؤ��Ƹ����С�
  �������㳰(cygwin �ξ��)�����������ϥ��ꥸ�ʥ��ǤȥХ��ʥ��٥�Ǥ�
  ��̸ߴ���������ޤ��Τǡ����Τޤޥ��ꥸ�ʥ��Ǥ��֤������뤳�Ȥ��Ǥ��ޤ���

  SIMD �б�������Ƥ�����ʬ�ϡ��ʲ��ΤȤ��ꡧ

  ���̽�����
    �������Ѵ�(RGB->YCbCr)  : MMX or SSE2
    �����󥵥�ץ��      : MMX or SSE2
    DCT���Ѵ�(����������)   : MMX or SSE2
    DCT���Ѵ�(��®����)     : MMX or SSE2
    DCT���Ѵ�(��ư����)     : 3DNow! or SSE (�����黻��: MMX or SSE2)
    DCT�����̻Ҳ�(����)     : MMX or SSE2
    DCT�����̻Ҳ�(��ư����) : 3DNow! or SSE (�����黻��: MMX or SSE2)

  Ÿ��������
    �������Ѵ�(YCbCr->RGB)  : MMX or SSE2
    ���åץ���ץ��      : MMX or SSE2
    DCT���Ѵ�(����������)   : MMX or SSE2
    DCT���Ѵ�(��®����)     : MMX or SSE2
    DCT���Ѵ�(��ư����)     : 3DNow! or SSE (�����黻��: MMX or SSE2)
    DCT���Ѵ�(�̾�Ÿ��)     : MMX or SSE2

  ���SSE2 �ˤĤ��Ƥϡ�SIMD �����黻�Τߤ����Ѥ��Ƥ��ޤ���SIMD ������
      ��ư�������黻�����Ѥ��Ƥ��ޤ��󡣤ޤ���SSE3 �ϻ��Ѥ���Ƥ��ޤ���
      ���� JPEG �饤�֥��ˤ����Ƥϡ�SSE3 ����Ѥ��Ƥ�ư��®�ٸ����
      �����ߤ��ۤȤ�ɤʤ�����ǡ�SSE3 �򥵥ݡ��Ȥ���ͽ��Ϥ���ޤ���

  ���Τۤ��ˡ�������֥������DCT�롼����(��SIMD; ���Ѵ�������Ѵ�����)
  �ˤ�ꡢSIMD̿��λȤ��ʤ��췿CPU�Ǥ⽽�������٤ι�®�������ԤǤ��ޤ���
  ����ˡ�Ÿ�������ǤΥϥեޥ�ǥ����ɥ롼����ϡ�SIMD ���˰ͤ�ʤ���ˡ��
  ��®����¤����Ƥ��ޤ���


���б����Ƥ���ץ�åȥե�����

  Intel x86 CPU �˸�ͭ�ε�ǽ�����Ѥ��Ƥ��ޤ��Τǡ����ꥸ�ʥ��ǤȤϰۤʤꡢ
  Intel x86 CPU ����Ӥ��θߴ� CPU ����Ѥ��Ƥ��륷���ƥ�˸¤��ޤ���
  PowerPC �ʤɤ� Intel x86 �ϰʳ��Υ����ƥ�ˤ��б����Ƥ��ޤ���
  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  ����Ū�ˤϡ�80386 �ʹߤ� Intel x86 CPU ����Ӥ��θߴ� CPU ����Ѥ��Ƥ���
  �ϡ��ɥ������ǡ����ġ�32bit�ե�åȥ��ɥ쥹�⡼��(�ݸ�⡼��)����Ѥ���
  ����ץ�åȥե�����(OS)���оݤǤ�������ˤϡ�Win32 (Windows 9x��/NT��)
  ��Ƽ� PC-UNIX (linux �� xBSD �ե��ߥ�ʤ�) �ʤɤ��������ޤ����ʤ���
  AMD64 (EM64T) ��64bit�⡼�ɴĶ��ˤ��б����Ƥ��ޤ��󡣤���դ���������
  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

������ SIMD ��ĥ�� IJG JPEG library ��ͭ������

  ���ꥸ�ʥ��Ǥ� IJG JPEG library �Ǥϡ�����ѥ�����Υ��ץ����ǡ�
  8bit����JPEG �� 12bit����JPEG ��ξ�����б����ޤ��������� SIMD ��ĥ�Ǥ�
  8bit����JPEG �Τߤ��б��ǡ�12bit����JPEG �ˤ��б����ޤ��󡣤ȤϤ�����
  12bit����JPEG �ϰ����Ѥʤɤ��ü�ʬ���������ؤɻȤ��Ƥ��ʤ��Τǡ�
  ����Ͼ��ʤ��Ȼפ��ޤ���


���Ȥ���

  �ޥ˥奢��ϡ��ʲ��Υե������ʬ����Ƥ��ޤ��Τǡ��ºݤλȤ����ʤɤ�
  �Ĥ��Ƥϡ�������򻲾Ȥ��Ƥ���������

    simd_README.ja.txt   - ���Υե�����
    simd_filelist.ja.txt - ��Ͽ�ե�����Υե�����ꥹ��
    simd_install.ja.txt  - ����ѥ���λ���
    simd_internal.ja.txt - SIMD ��ĥ��ʬ�ξܺ�
    simd_cdjpeg.ja.txt   - SIMD �� cjpeg/djpeg �˸�ͭ�ε�ǽ�β���
    simd_changes.ja.txt  - SIMD ��ĥ��ʬ�β�������


�����Ѿ����ݡ���

  ���� SIMD ��ĥ�� IJG JPEG software �λ��Ѿ��ˤĤ��Ƥϡ����ꥸ�ʥ��Ǥ�
  IJG JPEG software �λ��Ѿ�郎Ŭ�Ѥ���ޤ����ܤ����ϡ�Ʊ���� README
  �ե�����(��ʸ)�� LEGAL ISSUES �ι�򻲾Ȥ��Ƥ���������

  �嵭�λ��Ѿ������Ƥη����֤��ˤʤ�ޤ��������Υ��եȥ������ϡָ�����
  �ޤޤǡ��󶡤���Ƥ����Τǡ�����Ū�ʻ��Ѳ�ǽ����������������Ū��
  �Ф���Ŭ�����ʤɤ�ޤᡢ�����ʤ��ݾڤ⤢��ޤ���
  �ޤ��������(The Independent JPEG Group)���¤��(MIYASAKA Masaru)�⡢
  ��ͳ�Τ��������鷺���ܥ��եȥ������λ��Ѥˤ�ä�ȯ������ǡ���ʤ�»����
  �Ĥ��Ƥ⡢���ڤ�����Ǥ�����ʤ���ΤȤ��ޤ���

  ���� SIMD ��ĥ�� IJG JPEG software �ϡ����ꥸ�ʥ볫ȯ���� IJG �Ȥϴط�
  �ʤ����ȼ��˳�ĥ��Ԥʤä���ΤǤ����Ǥ��Τǡ����� SIMD ��ĥ�� IJG JPEG
  software �˴ؤ������򡢥��ꥸ�ʥ볫ȯ�� (The Independent JPEG Group)
  ������ʤ��Ǥ���������

  ���� SIMD ��ĥ�� IJG JPEG software �˴ؤ��Ƥϡ���§�Ȥ��ƥΡ����ݡ��Ȥ�
  �����Ƥ��������ޤ����᡼��ʤɤǤ�����ʤɤ򤤤������ޤ��Ƥ⡢��˲��餫
  ���������Ǥ���櫓�ǤϤ���ޤ���Τǡ������Τ�������������
  �äˡ��ʥ��ꥸ�ʥ�α�ʸ�ޥ˥奢���ޤ��Ʊ���Υޥ˥奢����˲�����
  �񤤤Ƥ������䡢���ѼԤΥ��եȥ��������ѼԤȤ��Ƥε�����­���и���­��
  �ؤ����䡢��������Τ����ʤ�����ʤɤˤĤ��Ƥϡ������򤤤����ޤ���Τǡ�
  �������餺��λ������������



           E-Mail Address : alkaid@coral.ocn.ne.jp (�ܺ� ��/MIYASAKA Masaru)
[EOF]
