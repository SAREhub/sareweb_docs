Przechwytywanie informacji z formularzy
=======================================

Aby zbierać informacje przekazane w formularzu należ wpiąć kody śledzące (główne) na daną stronę oraz wywołać odpowiednią metodę po zdarzeniu kliknięcia w przycisk zapisu formularza:
w przypadku gdy formularz przeładowuje stronę należy wykonać metodę sareX_params.event podając interesujące nas parametry przekazane w formularzu. Przykład:

.. code-block:: javascript

   sareX_params.event = {'id': '5', 'params' : {'_email' : 'abc@def', '_extra' : {'imie': 'imie', 'nazwisko' : 'nazwisko'}}};

gdzie wartość parametru id = 5 oznacza wywołanie zdarzenia submit. W parametrze **'_email'** należy podać adres email osoby wypełniającej formularz (lub zostawić to pole puste), natomiast w parametrze **'_extra'** można umieścić wszystkie interesujące nas dane.

W przypadku gdy zdarzenie wywoływane jest bez ponownego wejścia na stronę (odświeżenia) należy wywołać metodę:

.. code-block:: javascript

   var execute_params = {'_email': 'abc@def', '_extra' : {'imie': 'imie', 'nazwisko' : 'nazwisko'}};
   sareX_core.execute(5, execute_params);

