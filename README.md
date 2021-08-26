# APCS-thesis-template

This is our Overleaf thesis template for our university program APCS (VNU-HCM).

We are:
* Lê Phạm Ngọc Yến:
  * Student ID: 1751028
  * Email: lpnyen@apcs.vn
* Trần Thị Anh Thư:
  * Student ID: 1751036
  * Email: ttathu@apcs.vn

Our thesis topic: INTEGRATING NÔM LANGUAGE MODEL INTO NÔM OPTICAL CHARACTER RECOGNITION. (2021)

Both of us promise (to ourselves lol) that if our final score for our thesis exceed a threshold then we will make this template public.

This template does not contain everything that I use in my thesis as I only add more when we need it. <br>
However, in this README, I will try my best explain thing that I find useful during the writing process. <br>
Hopefully, you will find this template somewhat suitable to your need because I spent more than a day to gather everything :>

============================================================================================ <br>
You will only need to download ``APCS-thesis-template.zip`` and ``thesis-cd-cover.drawio``. <br>
``APCS-thesis-template.pdf`` is only a preview for you to know how the template will render.

**IMPORTANT: THIS TEMPLATE NEED TO BE RENDERED USING XeLaTeX.**
============================================================================================ <br>

**SOME INSTRUCTIONS:**

* ``preliminaries`` folder is where I store front matter .tex file like **thesis proposal**, **acknowledgement**, etc.
* ``cover-templates`` folder is where I store cover templates like **main cover**, **title page**, etc. <br>
  However, I also put ``comments-of-thesis-advisor.tex`` and ``comments-of-thesis-reviewer.tex`` in there because I we only need theses 2 files after thesis defense. But you can to move them to ``preliminaries`` folder if you want, just remember to change these 2 code lines:

  ``\input{cover-templates/comments-of-thesis-advisor}`` <br>
  ``\input{cover-templates/comments-of-thesis-reviewer}``

* ``figures``, ``fonts`` and ``ref`` are as name suggest.
* ``configurations.tex`` is the file that I put most of my packages and commands. I separate packages and commands according to (self-defined) categories like **pape setup*, **font setup**, etc. so that I can track thing easier but you can throw them everywhere I guess. What floats your boat.
* ``thesis.tex`` is the main .tex file.

* **TIP**: I give you the ``chapters`` folder to store individual chapter. However, I do recommend you dump everything in ``thesis.tex`` or writing all chapters in another .tex file then import in ``thesis.tex``. That way, the "File outline" panel to your left hand will render your entire thesis outline.

============================================================================================ <br>

**SOME (USEFUL) TIPS:**

* **Write Nôm scipt:**

  We almost given up on writing our thesis on Overleaf because we have to write in English, Quốc Ngữ script (current Vietnamese), Nôm script (old Vietnamese), and Han script (Chinese), but to cite, reference, write math equation, etc. on Word is a total nightmare for us. So I tried my best to find a way to write Nôm Script on Overleaf and here's how:
  
  Overleaf support this way of rendering Unicode: ``\char"<unicode>`` (1); therefore, to write Nôm script, you need to find its unicode. But the code (1) is not enough, you need to encapsulate it in a font environment, hence, you will need to import font as follows:
  
  1. Put your true-type font into ``fonts`` folder.
  2. Using this command to import it: ``\newfontfamily{<font-cmd-name>}{<actual-font-name>}[Path = ./fonts/, Extension = .ttf]`` <br>
  (I have import 2 fonts for this template so you can look at them and do as such.

  To write Nôm script, you will need 3 fonts: ``nomnatonglight.ttf``, ``HanaMinA.ttf``, and ``HanaMinB.ttf``. Most of the time I use *nomnatong*, but in some occasions I need *HanaMin*. Declare command for these fonts then encapsulate the code (1), e.g., I declare *nomnatong* as ``\nnt`` then write ``\nnt{\char"<unicode>}`` (2). If you find that writing this code line effect other text then put curly brackets around it, e.g. ``{\nnt{\char"<unicode>}}``. You can also declare a quick command for (2) like me: <br>
  ``\newcommand{\uc}[1]{{\nnt{\char"#1}}}`` <br>
  Then later you will only need to write ``\uc{<unicode>}``.
  
* **Center images that have width bigger than margin:** <br>
  Credit: https://tex.stackexchange.com/questions/16582/center-figure-that-is-wider-than-textwidth

  I use ``\centerfloat`` command a lot because the margin of the thesis template is quite large, leaving not so much space for the text. So I do occasionally have some tables or images that are large than ``\textwidth`` so I would use this command to center my tables and images.
  
* **Include images and table sideway:**

  If you want your image turn 90 degree while its caption still remain horizontal then you just need to use the ``angle`` variable: <br>
  ``\includegraphics[..., angle=90]{<image-path>}``
  
  But if you want your caption to turn along with your image then encapsulate your image in ``sidewaysfigure`` environment. For example: <br>
  ```
  \begin{sidewaysfigure}
      \centerfloat
      \includegraphics[...]{<image-path>}
      \caption{...}
      \label{fig:...}
  \end{sidewaysfigure}
  ```
  
  This is the same for table but table will be encapsulated in ``sidewaystable`` instead.
  
* **Some useful parameters when include images:**

  1. ``trim = {<left> <lower> <right> <upper>}``: to trim border around image.
  2. ``height`` and ``width``: to adjust image size (else the imported image will have original size). <br>
     Remember to include ``\textheight`` or ``\textwidth`` after the number, e.g., ``width=2.6in\textwidth``.
  3. There is also a ``keepaspectratio`` parameter to use when you use both ``height`` and ``width``.

* **Some useful tips when writing tables:**

  1. ``thead`` command: this command is very useful if you want to write multiple lines in a table cell or you want a cell to have different alignment. For example:
     ```
     \begin{table}[!h]
       \centerfloat
       \begin{tabular}{|c|}
         \hline
         \thead[l]{Hello\\world} \\
         \hline
         Hello world \\
         \hline
       \end{tabular}
       \caption{...}
       \label{tab:...}
     \end{table}
     ```
     
     The 1st row will have the word *Hello world* written in 2 lines AND left align (by indicate in ``\thead[<align-mode>]{<text>}`` where ``<align-mode>`` is ``l`` for left). The 2nd row will have *Hello world* written on the same line and center aligned as indicate in ``\begin{tabular}{|c|}``.
     
  2. Have table borders be thicker. Import package ``tabu`` then replace ``\begin{tabular}`` and ``\end{tabular}`` with ``\begin{tabu}`` and ``\end{tabu}``.

     * For horizontal border to be thicker, call command ``\tabucline[<thickness>]{-}`` instead of ``\hline``.
     * For vertical border to be thicker, write like this example ``\begin{tabu}{|[<thickness>]c|c|l|[<thickness>]l|}``. The ``[<thickness>]`` will affect the ``|`` before it.
