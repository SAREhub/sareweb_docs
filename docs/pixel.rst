############################
Piksel śledządzy
############################


Wstęp do wdrażania i testów
=======================================
Piksel śledzący jest najprostszym sposobem integracji z SAREweb.
Wykorzystanie piksela śledzącego jest wygodniejsze, ponieważ cały proces będzie można zredukować nawet do umieszczenia pojedynczego linku na stronie.


Podstawy wdrożenia i testów
=======================================

Zanim zaczniesz wywoływać piksel śledzący pamiętaj, aby poznać swój unikalny identyfikator z panelu SAREhub.
Podczas wysyłania zdarzeń będziemy mieli do czynienia z ustawieniem parametrów takich jak:

    - **domain** - Unikalny identyfikator z panelu SAREhub.
    - **email** -  Nie jest wymagany. Adres email użytkownika.
    - **user_id** - Nie jest wymagany. Unikalny identyfikator użytkownika.
    - **cart_event** - Przyjmuje typ zdarzenia koszykowego. Należy wybrać jedno z:
        - category_seen,
        - product_seen,
        - cart_added_product,
        - cart_removed_product,
        - cart_changed_product_quantity,
        - cart_checkout_started,
        - cart_checkout_delivery,
        - cart_checkout_payment,
        - cart_checkout_summary,
        - cart_checkout_confirm,
        - cart_checkout_completed
    - **product_id** - Identyfikator produktu zgodny z product feedem.
    - **quantity** - Przyjmuje ilość produktów. Dotyczy tylko zdarzeń:
        - cart_added_product,
        - cart_changed_product_quantity
    - **cart_id** - Nie jest wymagany. Przyjmuje unikalny identyfikator koszyka.
    - **country** - Nie jest wymagany. Domyślnie zostanie ustawiona wartości **PL**. Przyjmuje wartość kraju docelowego product feeda w formacie ISO 3166-1 alfa-2.
    - **language** - Nie jest wymagany. Domyślnie zostanie ustawiona wartości **pl**. Przyjmuje wartość języka w jakim przygotowany jest product feed w formacie ISO 639-1.


Każde zdarzenie można dodatkowo wzbogacić o tagi UTM:

    - **utm_source**
    - **utm_medium**
    - **utm_term**
    - **utm_content**
    - **utm_campaign**


Poprzez wysyłanie zdarzeń można dodatkowo otagować użytkownika w SAREhub:

    - **tags** - przyjmuje pojedyńczy tag lub listę tagów rozdzielonych przecinkiem.


Przykłady wdrażania i testów
=======================================


Przejście w kategorię produktu
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=category_seen&category_id=1


Przejście na stronę produktu
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=product_seen&product_id=1


Dodania produktu do koszyka
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_added_product&product_id=1&quantity=2


Usunięcia produktu z koszyka
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_removed_product&product_id=1


Zmiana liczby produktów w koszyku
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_changed_product_quantity&product_id=1&quantity=5

Parametr **quantity** powinien przyjmować wartość aktualnego stanu ilości produktu w koszyku, przykładowo jeśli w koszyku były 3 jednostki danego produktu i zwiększamy ilość o 2j. (czyli w sumie na 5j.) wartość parametru **quantity** będzie wynosić 5.


Rozpoczęcie procesu zamówienia
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_started


Podanie danych osobowych
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_registration


Wybór formy dostarczenia
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_delivery


Wybór sposobu płatności
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_payment


Podsumowanie koszyka
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_summary


Potwierdzenie zakupu
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_confirm


Finalizacja zakupu
---------------------------------------

.. code-block:: javascript

   https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_checkout_completed



Przykłady wywolania
---------------------------------------

Wywołanie z użyciem jQuery:

.. code-block:: javascript

    $.get('https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_added_product&product_id=1&quantity=2');



Umieszcznie w kodzie HTML:

.. code-block:: HTML

    <img height="1" width="1" src="https://api.sare25.com/collect?domain=<unikalny_identyfikator>&email=<test@sarehub.pl>&cart_event=cart_added_product&product_id=1&quantity=2">


