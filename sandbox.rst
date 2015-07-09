:orphan:

=====================================================
 The reStructuredText_ Cheat Sheet: Syntax Reminders
=====================================================
:Info: See <http://docutils.sf.net/rst.html> for introductory docs.
:Author: David Goodger <goodger@python.org>
:Date: $Date: 2013-02-20 01:10:53 +0000 (Wed, 20 Feb 2013) $
:Revision: $Revision: 7612 $
:Description: This is a "docinfo block", or bibliographic field list

.. NOTE:: If you are reading this as HTML, please read
   `<cheatsheet.txt>`_ instead to see the input syntax examples!

Section Structure
=================
Section titles are underlined or overlined & underlined.

Body Elements
=============
Grid table:

+--------------------------------+-----------------------------------+
| Paragraphs are flush-left,     | Literal block, preceded by "::":: |
| separated by blank lines.      |                                   |
|                                |     Indented                      |
|     Block quotes are indented. |                                   |
+--------------------------------+ or::                              |
| >>> print 'Doctest block'      |                                   |
| Doctest block                  | > Quoted                          |
+--------------------------------+-----------------------------------+
| | Line blocks preserve line breaks & indents. [new in 0.3.6]       |
| |     Useful for addresses, verse, and adornment-free lists; long  |
|       lines can be wrapped with continuation lines.                |
+--------------------------------------------------------------------+

Simple tables:

================  ============================================================
List Type         Examples (syntax in the `text source <cheatsheet.txt>`_)
================  ============================================================
Bullet list       * items begin with "-", "+", or "*"
Enumerated list   1. items use any variation of "1.", "A)", and "(i)"
                  #. also auto-enumerated
Definition list   Term is flush-left : optional classifier
                      Definition is indented, no blank line between
Field list        :field name: field body
Option list       -o  at least 2 spaces between option & description
================  ============================================================

================  ============================================================
Explicit Markup   Examples (visible in the `text source`_)
================  ============================================================
Footnote          .. [1] Manually numbered or [#] auto-numbered
                     (even [#labelled]) or [*] auto-symbol
Citation          .. [CIT2002] A citation.
Hyperlink Target  .. _reStructuredText: http://docutils.sf.net/rst.html
                  .. _indirect target: reStructuredText_
                  .. _internal target:
Anonymous Target  __ http://docutils.sf.net/docs/ref/rst/restructuredtext.html
Directive ("::")  .. image:: images/biohazard.png
Substitution Def  .. |substitution| replace:: like an inline directive
Comment           .. is anything else
Empty Comment     (".." on a line by itself, with blank lines before & after,
                  used to separate indentation contexts)
================  ============================================================

Inline Markup
=============
*emphasis*; **strong emphasis**; `interpreted text`; `interpreted text
with role`:emphasis:; ``inline literal text``; standalone hyperlink,
http://docutils.sourceforge.net; named reference, reStructuredText_;
`anonymous reference`__; footnote reference, [1]_; citation reference,
[CIT2002]_; |substitution|; _`inline internal target`.

Directive Quick Reference
=========================
See <http://docutils.sf.net/docs/ref/rst/directives.html> for full info.

================  ============================================================
Directive Name    Description (Docutils version added to, in [brackets])
================  ============================================================
attention         Specific admonition; also "caution", "danger",
                  "error", "hint", "important", "note", "tip", "warning"
admonition        Generic titled admonition: ``.. admonition:: By The Way``
image             ``.. image:: picture.png``; many options possible
figure            Like "image", but with optional caption and legend
topic             ``.. topic:: Title``; like a mini section
sidebar           ``.. sidebar:: Title``; like a mini parallel document
parsed-literal    A literal block with parsed inline markup
rubric            ``.. rubric:: Informal Heading``
epigraph          Block quote with class="epigraph"
highlights        Block quote with class="highlights"
pull-quote        Block quote with class="pull-quote"
compound          Compound paragraphs [0.3.6]
container         Generic block-level container element [0.3.10]
table             Create a titled table [0.3.1]
list-table        Create a table from a uniform two-level bullet list [0.3.8]
csv-table         Create a table from CSV data [0.3.4]
contents          Generate a table of contents
sectnum           Automatically number sections, subsections, etc.
header, footer    Create document decorations [0.3.8]
target-notes      Create an explicit footnote for each external target
math              Mathematical notation (input in LaTeX format)
meta              HTML-specific metadata
include           Read an external reST file as if it were inline
raw               Non-reST data passed untouched to the Writer
replace           Replacement text for substitution definitions
unicode           Unicode character code conversion for substitution defs
date              Generates today's date; for substitution defs
class             Set a "class" attribute on the next element
role              Create a custom interpreted text role [0.3.2]
default-role      Set the default interpreted text role [0.3.10]
title             Set the metadata document title [0.3.10]
================  ============================================================

Interpreted Text Role Quick Reference
=====================================
See <http://docutils.sf.net/docs/ref/rst/roles.html> for full info.

================  ============================================================
Role Name         Description
================  ============================================================
emphasis          Equivalent to *emphasis*
literal           Equivalent to ``literal`` but processes backslash escapes
math              Mathematical notation (input in LaTeX format)
PEP               Reference to a numbered Python Enhancement Proposal
RFC               Reference to a numbered Internet Request For Comments
raw               For non-reST data; cannot be used directly (see docs) [0.3.6]
strong            Equivalent to **strong**
sub               Subscript
sup               Superscript
title             Title reference (book, etc.); standard default role
================  ============================================================


End of The reStructuredText_ Cheat Sheet
========================================

=======================
Examples from our docs:
=======================

**Typographic Conventions** 

* Names of graphical elements such as buttons, icons, fields, columns, and boxes are enclosed within quotes. For example: click the "Browse Categories" button.

* Menu selections are italicized and separated by arrows. For example: :menuselection:`Control Panel --> About`.

* Commands that are mentioned within text are highlighted in :command:`bold text`. Command examples and command output are contained in green code blocks.

* File names are enclosed in a blue box :file:`/like/this`.

* Keystrokes are formatted in a blue box. For example: press :kbd:`Enter`.

* **bold text** is used to emphasize an important point.

* *italic text* is used to represent device names or text that is input into a GUI field.

Table 1.3a summarizes the various filesystems commonly used by desktop systems. Most of the desktop managers available from PC-BSD® should automatically
mount the following filesystems: FAT16, FAT32, EXT2, EXT3 (without journaling), EXT4 (read-only), NTFS5, NTFS6, and XFS. See the section on
:ref:`Files and File Sharing` for more information about available file manager utilities.

**Table 1.3a: Filesystem Support on PC-BSD®**

+------------+-------------------+------------------------------------------------+--------------------------------------------------------------------------+
| Filesystem | Native to         | Type of non-native support                     | **Usage notes**                                                          |
+============+===================+================================================+==========================================================================+
| Btrfs      | Linux             | none                                           |                                                                          |
+------------+-------------------+------------------------------------------------+--------------------------------------------------------------------------+
| exFAT      | Windows           | none                                           | requires a license from Microsoft                                        |
+------------+-------------------+------------------------------------------------+--------------------------------------------------------------------------+
| EXT2       | Linux             | r/w support loaded by default                  |                                                                          |
+------------+-------------------+------------------------------------------------+--------------------------------------------------------------------------+
| EXT3       | Linux             | r/w support loaded by default                  | since EXT3 journaling is not supported, you will not be able to mount    |
|            |                   |                                                | a filesystem requiring a journal replay unless you :command:`fsck` it    |
|            |                   |                                                | using an external utility such as                                        |
|            |                   |                                                | `e2fsprogs <http://e2fsprogs.sourceforge.net>`_                          |
+------------+-------------------+------------------------------------------------+--------------------------------------------------------------------------+


.. index:: hardware
.. _Supported Hardware:

Supported Hardware 
==================

PC-BSD® should install on any system containing a 64-bit (also called amd64) processor. Despite the amd64 name, a 64-bit processor does **not need** to be
manufactured by AMD in order to be supported. The `FreeBSD Hardware Notes <http://www.freebsd.org/releases/10.1R/hardware.html#proc>`_ list the amd64
processors known to work.

Like most open source operating systems, PC-BSD® uses X.org drivers for graphics support. PC-BSD® will automatically detect the optimal video settings for
supported video drivers. You can verify that your graphics hardware is supported by clicking the :ref:`Hardware Compatibility` icon within the installer.

Support for the major graphic vendors is as follows: 

**NVIDIA:** if you want to use 3D acceleration, NVIDIA is currently the best supported as there is a native driver for PC-BSD®. If an NVIDIA video card is
detected, an "nVidia settings" icon will be added to the Control Panel for managing NVIDIA settings.

**Intel:** 3D acceleration on most Intel graphics is supported.

**ATI/Radeon:** 3D acceleration on most ATI and Radeon cards is supported.

**Optimus:** at this time there is no switching support between the two graphics adapters provided by Optimus. Optimus implementations vary, so PC-BSD® may
or may not be able to successfully load a graphics driver on your hardware. If you get a blank screen after installation, check your BIOS to see if it has an
option to disable one of the graphics adapters or to set "discrete" mode. If the BIOS does not provide a discrete mode, PC-BSD® will default to the 3D Intel
driver and disable NVIDIA. This will change in the future when the NVIDIA driver supports Optimus.

A list of graphics cards which are known to work can be found on the `FreeBSD Graphics Wiki <https://wiki.freebsd.org/Graphics>`_.

PC-BSD® has built-in support for dozens of wireless networking cards. You can check if your card has a
`FreeBSD driver <http://www.freebsd.org/releases/10.1R/hardware.html#WLAN>`_. If it does, it should "just work". A list of
supported Atheros devices and known limitations can be found on the `Status of Atheros Wifi Hardware wiki page <https://wiki.freebsd.org/dev/ath_hal%284%29/HardwareSupport>`_.
A list of supported Intel devices and known limitations can be found on the `iwn(4) Intel 802.11n series NICs wiki page <https://wiki.freebsd.org/dev/iwn%284%29>`_.

PC-BSD® will automatically detect available wireless networks for supported wireless devices. You can verify that your device is supported by clicking the
:ref:`Hardware Compatibility` icon within the installer. If it an external wireless device, insert it before running the "Hardware Compatibility" utility.

Certain Broadcom devices, typically found in cheap laptops, are quite buggy and can have lockups when in DMA mode. If the device freezes, try switching to "PIO"
mode in the BIOS. Alternately, add the line *hw.bwn.usedma=0* to :file:`/boot/loader.conf` and reboot to see if that makes a difference. 

If you wish to check your hardware before installing PC-BSD®, a good place to start is the
`FreeBSD Hardware Notes <http://www.freebsd.org/releases/10.1R/hardware.html>`_. Another good resource is to start the installer and click the
:ref:`Hardware Compatibility` icon.

While most hardware "just works" with PC-BSD®, it is possible that you will run across a piece of hardware that does not. It should be remembered that
PC-BSD® is really FreeBSD, meaning that any hardware that works on FreeBSD will work on PC-BSD®. If you are experiencing problems with a device, start with
a web search for the term "FreeBSD" plus the type and model of the hardware. This will let you know if there is a known issue with the device. If there are
many search results, concentrate on the most recent ones as often hardware that used to be problematic has since been fixed or the missing driver will be
available in an upcoming release of FreeBSD. If you experience problems with a device that should work but does not or you can not find any existing problem
reports for your hardware, you can help improve hardware support for all PC-BSD® users if you :ref:`Report a bug` so that it can be addressed by the
developers.

.. index:: laptops
.. _Laptops:

Laptops
-------

Many PC-BSD® users successfully run PC-BSD® on their laptops. However, depending upon the model of laptop, you may run across some issues. These typically
deal with: 

* **Sleep/suspend:** unfortunately, `ACPI <http://en.wikipedia.org/wiki/Advanced_Configuration_and_Power_Interface>`_ is not an exact science, meaning that
  you may have to experiment with various :command:`sysctl` variables in order to achieve successful sleep and suspend states on your particular laptop model.
  If your laptop is a ThinkPad, `ThinkWiki <http://thinkwiki.org/>`_ is an excellent source. For other types of laptops, try reading the "SYSCTL VARIABLES"
  section of :command:`man 4 acpi` and check to see if there is an ACPI man page specific to your vendor by typing :command:`apropos acpi.` The
  `Tuning with sysctl(8) <http://www.freebsd.org/doc/en/books/handbook/configtuning-sysctl.html>`_ section of the FreeBSD Handbook demonstrates how to
  determine your current :command:`sysctl` values, modify a value, and make a modified value persist after a reboot. If the battery reading is incorrect, try
  the workaround in this `PR <http://www.freebsd.org/cgi/query-pr.cgi?pr=kern/160838>`_.

* **Internal wireless:** some chipsets do not have a FreeBSD driver yet.

* **Synaptics:** depending upon the hardware, you may or may not be able to disable the system's touchpad. This
  `forum post <http://forums.freebsd.org/viewtopic.php?s=63c71cacb981215c14b64b74481d17cd&p=100670&postcount=17>`_ describes how to enable Synaptics and some
  of the :command:`sysctl` options that this feature provides.

* **Optimus graphics:** the current workaround is to disable Optimus in the BIOS, set the onboard Intel video to be dominant, or to change the graphics mode
  to discrete.

If you wish to test your laptop's hardware, use the "Hardware Compatibility" icon in the :ref:`Language Selection Screen` before continuing with the
installation.

If you would like to install PC-BSD® onto an Asus Eee, read the `FreeBSD Eee page <http://wiki.freebsd.org/AsusEee>`_ first.

The `FreeBSD Tuning Power Consumption page <http://wiki.freebsd.org/TuningPowerConsumption>`_ has some tips for reducing power consumption.

.. index:: thinkpad

With regards to specific hardware, the ThinkPad T420 may panic during install. If it does, go into the BIOS and set the video mode to "discrete" which should allow you to complete an
installation. Some Thinkpads have a BIOS bug that prevents them from booting from GPT labelled disks. If you are unable to boot into a new installation, restart the
installer and go into "Advanced Mode" in the :ref:`Disk Selection Screen`. Make sure that the "Partition disk with GPT" box is unchecked. If it was checked
previously, redo the installation with the box unchecked.

.. index:: hardware
.. _Touch Screens:

Touch Screens 
--------------

PC-BSD® should automatically detect USB-based touch screen devices. If your display is USB and is not auto-detected, send the output of :command:`usbconfig`
and your :file:`/etc/X11/xorg.conf` file using the :ref:`Report a bug` tool.

.. index:: partition
.. _Partitioning the Hard Drive:

Partitioning the Hard Drive
===========================

PC-BSD® does not come with a built-in partition manager. The installer assumes that you will either install PC-BSD® to the entire drive or, when installing to a
specific partition, that the drive has already been divided into the desired number of partitions. In order to install PC-BSD® into a partition rather than to the
entire hard drive, you will need to use a third-party application to prepare a primary partition to use as the destination for your PC-BSD® install.

.. note:: PC-BSD® will not install into a secondary or logical partition, it must be a **primary** or a **GPT** partition.

.. warning:: **before** creating or editing your hard drive's partitions, make sure that you first back up your valuable data to an external media such as a
   removable USB drive!

This section demonstrates how to create free space within Windows 7 and how to use Parted Magic to create a primary partition from the free space.

If you are currently running Windows 7, it is using the entire hard drive. This means that you will need to first shrink the drive in order to make room to
create a new partition. Shrinking is an operation that retains the current data on the partition, while reducing the size of the partition.

To shrink the drive, go to :menuselection:`Start menu --> right-click Computer --> Manage --> Storage --> Disk Management`. Figure 2.3a shows an example of a
system running Windows 7. In this example, Windows has created three partitions: a 16GB recovery partition, a 100MB system partition, and a 450GB data
partition.

**Figure 2.3a: Viewing Disk Layout in Disk Management** 

.. image:: images/partition1.jpg

.. warning:: if you plan to dual-boot with Windows, it is important that you do not choose to install PC-BSD® into any of these three partitions when you get
   to the :ref:`Disk Selection Screen` of the installer. It is a good idea to write down the sizes of the partitions so that you will recognize them when the
   PC-BSD® installer displays your current partitions.

Since the three Windows partitions are using the entire disk, the data partition needs to be shrunk in order to create space to install PC-BSD® into. To
shrink the data partition, right-click the partition, in this example it is called *Acer (C:)*, and select "Shrink Volume". Wait a moment as it queries the
volume for available shrink space. The results will be displayed as seen in the example in Figure 2.3b. 

**Figure 2.3b: Available Shrink Space** 

.. image:: images/shrink1.jpg

In this example, 321089MB of space is available. To divide the partition between Windows and PC-BSD®, change that number to *230000* and click the "Shrink"
button. When finished, the newly created free space will be displayed, as seen in Figure 2.3c.

**Figure 2.3c: Disk Now Has Free Space** 

.. image:: images/shrink2.jpg

You can now format the newly created free space using a utility such as Parted Magic.

.. note:: while the Disk Management utility in Windows 7 indicates that it will let you format a primary partition, in reality it will only create an extended
   partition which will not allow you to install PC-BSD®. This means that you still need another utility such as Parted Magic.

`Parted Magic <http://sourceforge.net/projects/partedmagic>`_ is a graphical, easy-to-use partition editor that is packaged on a live CD. It can be used to
shrink an existing partition and to create a primary partition from existing free space.

To use Parted Magic, download the latest :file:`.iso.zip` file, unzip it, and burn it to CD. Boot the system with the CD and let it boot into "Default
settings (Runs from RAM)". Wait for it to boot into the graphical screen, then select the "Partition Editor" desktop icon.

Figure 2.3d shows the same Windows 7 system in Partition Editor. The 225.05GB partition is the Windows data partition (which was displayed as drive C within
Windows 7) and the 224.61GB of unallocated space was created using the Windows Disk Management utility. The "Create new Partition" screen was opened by
right-clicking on the unallocated space and selecting "New" from the menu.

**Figure 2.3d: Formatting the Unallocated Space into a Primary Partition** 

.. image:: images/parted1.png

When creating your partition from unallocated space, make sure that "Primary Partition" is selected. The filesystem type does not matter as the PC-BSD®
installer will reformat it. It is a good idea to write down the size and filesystem type so that you will recognize the partition that you will be installing
PC-BSD® into. Once you have made your selections, click the "Add" button.
