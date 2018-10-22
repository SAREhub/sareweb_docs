############################
Powiadomienia Push
############################


Dla stron z protokołem HTTPS
=======================================

Wymagany jest protokół HTTPS.
W kodzie strony musi znajdować się podstawowy kod śledzący SAREweb oraz dodatkowy parametr **webPush**.

.. code-block:: javascript

   (function (p){window['sareX_params']=p;var s=document.createElement('script');
   s.src='//x.sare25.com/libs/sarex4.min.js';
   s.async=true;var t=document.getElementsByTagName('script')[0];
   t.parentNode.insertBefore(s,t);
   })({
      domain : 'brak.pl',
      webPush: {}
   });


Następnie pobierz SDK: https://x.sare25.com/libs/sareweb_webpush.zip


Na koniec rozpakuj pliki SDK (**minifest.json** i **sw.js**) i dodaj je do głównego foldera (root) Twojej strony.



Dla stron z protokołem HTTP
=======================================

Nie jest wymagany protokół HTTPS.
W kodzie strony musi znajdować się podstawowy kod śledzący SAREweb oraz dodatkowy parametr **webPush** z parametrem **mode: popup**.

.. code-block:: javascript

   (function (p){window['sareX_params']=p;var s=document.createElement('script');
   s.src='//x.sare25.com/libs/sarex4.min.js';
   s.async=true;var t=document.getElementsByTagName('script')[0];
   t.parentNode.insertBefore(s,t);
   })({
      domain : 'brak.pl',
      webPush: {
         mode: 'popup'
      }
   });
   

Powiadomienia będą wysyłane z domeny sarepush.com

