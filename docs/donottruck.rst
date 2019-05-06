Śledzenie użytkowników
=======================================

Podstawowy kod śledzący SAREweb, który należy wstawić w kodzie źródłowym strony internetowej (pamiętając o podmianie identyfikatora wewnątrz kodu):

.. code-block:: HTML

    <script>
       (function (p){window['sareX_params']=p;var s=document.createElement('script');
       s.src='//x.sare25.com/libs/sarex4.min.js';
       s.async=true;var t=document.getElementsByTagName('script')[0];
       t.parentNode.insertBefore(s,t);
       })({
          domain : 'brak.pl',
          doNotTrack : true / false
       });
    </script>

W przypadku stron SPA jest możliwość dynamicznej zmiany opcji śledzenia poprzez wykorzystanie pomocniczych funkcji.


Wywołanie poniższej funkcji zablokuje wszystkie działania związane ze śledzeniem użytkownika.

.. code-block:: javascript

   sareX_core.doNotTrackEnable();


Wywołanie poniższej funkcji odblokuje wszystkie działania związane ze śledzeniem użytkownika.

.. code-block:: javascript

   sareX_core.doNotTrackDisable();

