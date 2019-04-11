############################
Zdarzenia koszykowe
############################

W celu identyfikacji zalogowanego użytkownika należy przekazać jego unikalny identyfikator w parametrze **'_userId'** oraz adres e-mail w parametrze **'_email'**.

Parametry **'_userId'** i **'_email'** powinny być wysyłane wraz z każdym zdarzeniem zalogowanego użytkownika.

Jeśli adres e-mail **_email** lub **_userId** nie jest znany w momencie wykonania któregoś z poniższych zdarzeń to wartość powinna być pusta (lub null).

Jeśli identyfikatorem użytkownika jest adres e-mail to wartość  **'_userId'** i **'_email'** powinna być taka sama.

Jeśli adres e-mail nie jest znany po zalogowaniu użytkownika, wartość parametru **'_email'** będzie pusta (lub null).

Przejście w kategorię produktu
=======================================

.. code-block:: javascript

   sareX_params.tag = {'_userId': '123', '_email': 'abc@def', '_category': {'country' : 'PL', 'language': 'pl', 'id': 'nazwa kategorii'}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

	var execute_params = {'_userId': '123', '_email': 'abc@def', '_category': {'country' : 'PL', 'language': 'pl', 'id': 'nazwa kategorii'}};
	sareX_core.execute(10, execute_params);

Parametr **'country'** i **'language'** jest wymagany. Wartość parametru **'country'** przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2. Wartość parametru **'language'** przyjmuje wartość języka w jakim przygotowanych jest product feed w formacie ISO 639-1.


Przejście na stronę produktu
=======================================

.. code-block:: javascript

   sareX_params.tag = {'_userId': '123', '_email': 'abc@def', '_product': {'country' : 'PL', 'language': 'pl', 'id': '1', 'url' : 'URL produktu' }};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

	var execute_params = {'_userId': '123', '_email': 'abc@def', '_product': {'country' : 'PL', 'language': 'pl', 'id': '1', 'url' : 'URL produktu'}};
	sareX_core.execute(10, execute_params);

Parametr **'country'**, **'language'** i **'id'** jest wymagany. Wartość parametru **'country'** przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2. Wartość parametru **'language'** przyjmuje wartość języka w jakim przygotowanych jest product feed w formacie ISO 639-1. Parametr **'id'** to identyfikator produktu.


Dodania produktu do koszyka
=======================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : false, '_cartadd' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1', 'quantity' : 1, 'url' : 'URL produktu'}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : false, '_cartadd' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1', 'quantity' : 1, 'url' : 'URL produktu'}};
   sareX_core.execute(10, execute_params);

Parametr **'country'** i **'language'** jest wymagany. Wartość parametru **'country'** przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2. Wartość parametru **'language'** przyjmuje wartość języka w jakim przygotowanych jest product feed w formacie ISO 639-1.


Usunięcia produktu z koszyka
=======================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartdel' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1'}}};


W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartdel' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1'}};
   sareX_core.execute(10, execute_params);

Parametr **'country'** i **'language'** jest wymagany. Wartość parametru **'country'** przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2. Wartość parametru **'language'** przyjmuje wartość języka w jakim przygotowanych jest product feed w formacie ISO 639-1.


Zmiana liczby produktów w koszyku
==============================================================================

Parametr 'quantity' przyjmuje wartość na jaką ustawiana jest liczba danego produktu podczas jej edycji:

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartquantity' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1', 'quantity' : 1}}};


W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartquantity' : {'country' : 'PL', 'language': 'pl', 'cart_id' : '', 'product_id' : '1', 'quantity' : 1}};
   sareX_core.execute(10, execute_params);


Parametr **'country'** i **'language'** jest wymagany. Wartość parametru **'country'** przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2. Wartość parametru **'language'** przyjmuje wartość języka w jakim przygotowanych jest product feed w formacie ISO 639-1.

Parametr **'quantity'** powinien przyjmować wartość aktualnego stanu ilości produktu w koszyku, przykładowo jeśli w koszyku były 3 jednostki danego produktu i zwiększamy ilość o 2j. (czyli w sumie na 5j.) wartość parametru **'quantity'** będzie wynosić 5.

Rozpoczęcie procesu zamówienia
============================================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartinitialized' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartinitialized' : {'cart_id' : ''}}};
   sareX_core.execute(10, execute_params);

Podanie danych osobowych
============================================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartregistration' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartregistration' : {'cart_id' : ''}}};
   sareX_core.execute(10, execute_params);

Wybór formy dostarczenia
==============================================================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartdelivery' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartdelivery' : {'cart_id' : ''}}};
   sareX_core.execute(10, execute_params);

Wybór sposobu płatności
===========================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartpayment' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartpayment' : {'cart_id' : ''}};
   sareX_core.execute(10, execute_params);

Podsumowanie koszyka
============================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartsummary' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartsummary' : {'cart_id' : ''}};
   sareX_core.execute(10, execute_params);

Potwierdzenie zakupu
===========================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartconfirm' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartconfirm' : {'cart_id' : ''}};
   sareX_core.execute(10, execute_params);

Finalizacja zakupu
============================================

.. code-block:: javascript

   sareX_params.event = {'id': '10', 'params' : {'_userId': '123', '_email' : 'abc@def', '_cartpurchased' : {'cart_id' : ''}}};

W przypadku gdy zdarzenie powinno zostać wywołane dynamicznie czyli bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartpurchased' : {'cart_id' : ''}};
   sareX_core.execute(10, execute_params);


Problem asynchroniczności
============================================

Częsty problem developerów objawia się tym, że próbują oni wykorzystać bibliotekę, kiedy nie jest ona jeszcze załadowana.

Pierwszy sposób, poprzez wykorzystanie **window.onload**:

.. code-block:: javascript

    window.onload = function() {
       var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartpurchased' : {'cart_id' : ''}};
       sareX_core.execute(10, execute_params);
    }

Drugi sposób, z wykorzystaniem **window.addEventListener('DOMContentLoaded', ...)**:

.. code-block:: javascript

    window.addEventListener('DOMContentLoaded', function(event){
       var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartpurchased' : {'cart_id' : ''}};
       sareX_core.execute(10, execute_params);
    });

Trzeci sposób, dla stron gdzie jest wykorzystana biblioteka **jQuery**:

.. code-block:: javascript

    $(document).ready(function() {
       var execute_params = {'_userId': '123', '_email' : 'abc@def', '_cartpurchased' : {'cart_id' : ''}};
       sareX_core.execute(10, execute_params);
    });


