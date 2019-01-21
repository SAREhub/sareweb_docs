Personalizacja na stronie
=======================================

Podstawowy kod śledzący SAREweb, który należy wstawić stronie serwisu należy wzbogacić o dwa dodatkowe parametry **personalization_subject** oraz **personalization_callback**.

- **personalization_subject** - stworzony wcześniej w panelu SAREhub identyfikator personalizacji. Pozwala na personalizowanie konkretnej podstrony. Parametr jest tablicą co umożliwia podanie kilku identyfikatorów personalizacji.


- **personalization_callback** - funkcja callback przygotowana w Javascript, która wyzwoli personalizację np. personalization_handler.

Przykład:

.. code-block:: javascript

    (function (p){window['sareX_params']=p;var s=document.createElement('script');
    s.src='//x.sare25.com/libs/sarex4.min.js';s.async=true;var t=document.getElementsByTagName('script')[0];
    t.parentNode.insertBefore(s,t);
    })({
      domain : 'brak.pl',
      personalization_callback: personalization_handler,
      personalization_subject: ["popup"]
    });

    function personalization_handler(msg){
        if (msg.params.body.SAREhub_custom_229_typ) {
            var popup = $("#popup-container");
            popup.text(msg.params.body.SAREhub_custom_229_typ);
            popup.show();
        }
    }


Użyty parametr SAREhub_custom_229_typ jest przykładem, w panelu SAREhub można wyświtlić dostępne parametry dla personalizacji.