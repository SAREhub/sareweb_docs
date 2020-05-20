############################
Powiadomienia WebPush
############################


Dla stron z protokołem HTTPS
=======================================

Domena musi posiadać ważny certyfikat SSL oraz wymaga umieszczenia dwóch plików na serwerze.

1. Podstawowy kod śledzący SAREweb musi być umieszczony na stronie.

.. code-block:: HTML

 <script src="//cdn.sarehub.com/clients/<twój-identyfikator>.js" async></script>

2. Pobierz paczkę ze skryptami. Pobrany pakiet będzie zawierał dwa skrypty: **manifest.json** i **sw.js**.

Link do paczki: https://x.sare25.com/libs/sareweb_webpush.zip

3. Na koniec rozpakuj paczkę i dodaj pliki **minifest.json** i **sw.js** je do głównego folderu (root) strony.



