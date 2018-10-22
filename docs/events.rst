Wysyłanie zdarzeń
=======================================

sareX_params.tag - służy do tagowania danej strony np. oznaczeniem jej daną kategorią oraz przesyłania dodatkowych informacji w momencie wejścia na daną stronę. Przykład:

.. code-block:: javascript

   sareX_params.tag = {'_userId': '123', '_email': 'abc@def', '_category':{'id':'nazwa kategorii'}};

sareX_core.execute – służy do wysyłania informacji na temat danego zdarzenia w przypadku gdy zdarzenie wywoływane jest bez ponownego wejścia na stronę (odświeżenia). Przykład:

.. code-block:: javascript

   var event = 10;
   var execute_params = {'_userId': '123', '_email': 'abc@def', '_category':{'id':'nazwa kategorii'}};
   sareX_core.execute(event, execute_params);

- event - gdzie
    - 1 oznacza wejście na stronę,
    - 5 to zdarzenie wysłania formularza (szczegółowe informacje http://sareweb.readthedocs.io/pl/latest/form_events.html )
    - 10 to zdarzenie koszykowe (szczegółowe informacje http://sareweb.readthedocs.io/pl/latest/carts.html )


- execute_params – dodatkowe parametry wysyłane wraz z danym eventem. Wartość tego parametru musi być obiektem.
