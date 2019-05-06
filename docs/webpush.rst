############################
Powiadomienia WebPush
############################


Dla stron z protokołem HTTPS
=======================================

Ten sposób integracji jest możliwy tylko dla domen https oraz wymaga umieszczenia dwóch plików na serwerze.

1. Podstawowy kod śledzący SAREweb musi być umieszczony na stronie z dodatkowym parametrem **webPush**.

.. code-block:: HTML

    <script>
       (function (p){window['sareX_params']=p;var s=document.createElement('script');
       s.src='//x.sare25.com/libs/sarex4.min.js';
       s.async=true;var t=document.getElementsByTagName('script')[0];
       t.parentNode.insertBefore(s,t);
       })({
          domain : 'brak.pl',
          webPush : {}
       });
    </script>

2. Pobierz paczkę ze skryptami. Pobrany pakiet będzie zawierał dwa skrypty: **manifest.json** i **sw.js**.

Link do paczki: https://x.sare25.com/libs/sareweb_webpush.zip

3. Na koniec rozpakuj paczkę i dodaj pliki **minifest.json** i **sw.js** je do głównego folderu (root) strony.


Dla stron z protokołem HTTP
=======================================

W tym sposobie integracji nie jest wymagany protokół HTTPS. Powiadomienia będą wysyłane z domeny **twoj-idetyfikator**.sarepush.com

1. Podstawowy kod śledzący SAREweb musi być umieszczony na stronie z dodatkowym parametrem **webPush**.

W kodzie strony musi znajdować się podstawowy kod śledzący SAREweb oraz dodatkowy parametr **webPush**

opcja: **mode : popup**

.. code-block:: HTML

    <script>
       (function (p){window['sareX_params']=p;var s=document.createElement('script');
       s.src='//x.sare25.com/libs/sarex4.min.js';
       s.async=true;var t=document.getElementsByTagName('script')[0];
       t.parentNode.insertBefore(s,t);
       })({
          domain : 'brak.pl',
          webPush : {
             mode : 'popup'
          }
       });
    </script>


opcja: **mode: popover**
   
.. code-block:: javascript

    <script>
       (function (p){window['sareX_params']=p;var s=document.createElement('script');
       s.src='//x.sare25.com/libs/sarex4.min.js';
       s.async=true;var t=document.getElementsByTagName('script')[0];
       t.parentNode.insertBefore(s,t);
       })({
          domain : 'brak.pl',
          webPush : {
             mode : 'popover'
          }
       });
    </script>




