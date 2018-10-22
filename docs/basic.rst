Podstawowy kod śledzący
=======================================

Podstawowy kod śledzący SAREweb, który należy wstawić na stronie internetowej (pamiętając o podmianie domeny zawartej wewnątrz kodu):

.. code-block:: javascript

   (function (p){window['sareX_params']=p;var s=document.createElement('script');
   s.src='//x.sare25.com/libs/sarex4.min.js';s.async=true;var t=document.getElementsByTagName('script')[0];
   t.parentNode.insertBefore(s,t);
   })({
      domain : 'brak.pl'
   });


Dodatkowy parametr, który jest potrzebny do monitorowania czasu spędzonego na stronach.

.. code-block:: javascript

   ping : {'period0' : 10, 'period1' : 60},



Dodatkowy parametr, który informuje system INIS o wejściu na stronę.
Do podmiany:
- <kampania> = nazwa kampanii (np. 'campaign01')
- <strona> = nazwa strony (np. 'home')
- <uidy_w_sare> = uid lub lista uidow w SARE oddzielonych przecinkiem ([12] lub [12,31668])


.. code-block:: javascript

   inisTrack : {t:'p', c:'<kampania>',s:'<strona>', uid:[<uidy_w_sare>]}




