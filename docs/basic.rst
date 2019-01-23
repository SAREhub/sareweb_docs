Podstawowy kod śledzący
=======================================

Podstawowy kod śledzący SAREweb, który należy wstawić w kodzie źródłowym strony internetowej (pamiętając o podmianie identyfikatora wewnątrz kodu):

.. code-block:: javascript

   (function (p){window['sareX_params']=p;var s=document.createElement('script');
   s.src='//x.sare25.com/libs/sarex4.min.js';s.async=true;var t=document.getElementsByTagName('script')[0];
   t.parentNode.insertBefore(s,t);
   })({
      domain : 'brak.pl'
   });


Dodatkowe parametry do kodu śledzącego
----------------

Dodatkowy parametr wymagany do monitorowania czasu spędzonego na stronie internetowej.

.. code-block:: javascript

   ping : true


Dodatkowy parametr wymagany do integracji z Inis (wysyłki na e-mail zewnętrzny).

.. code-block:: javascript

   inisTrack : true


Parametr, który blokujący działanie skryptów śledzących podczas przeglądania strony internetowej przez użytkownika.

.. code-block:: javascript

   doNotTrack : true


Przykład kodu śledzącego z dodatkowymi parametrami
----------------

.. code-block:: javascript

   (function (p){window['sareX_params']=p;var s=document.createElement('script');
   s.src='//x.sare25.com/libs/sarex4.min.js';s.async=true;var t=document.getElementsByTagName('script')[0];
   t.parentNode.insertBefore(s,t);
   })({
      domain : 'brak.pl',
      ping : true,
      inisTrack : true
   });