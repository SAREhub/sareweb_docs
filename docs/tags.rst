Tagowanie użytkowników
=======================================

W przypadku gdy tagowanie użytkowników jest wywołane podczas przeładowania strony należy dodać poniższy kod.
Kod powinien znajdować się poniżej podstawowego kodu śledzącego.

.. code-block:: javascript

   sareX_params.addUserTags = ['buty', 'ubrania'];


W przypadku gdy tagowanie użytkowników wywoływane jest dynamicznie, bez ponownego wejścia na stronę należy wywołać metodę:

.. code-block:: javascript

   sareX_core.addUserTags(['buty', 'ubrania']);