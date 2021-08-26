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

=============================================================================================== <br>
You will only need to download ``APCS-thesis-template.zip`` and ``thesis-cd-cover.drawio``. <br>
``APCS-thesis-template.pdf`` is only a preview for you to know how the template will render.

**IMPORTANT: THIS TEMPLATE NEED TO BE RENDERED USING XeLaTeX.**
=============================================================================================== <br>

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

=============================================================================================== <br>

**SOME (USEFUL) TIPS:**
