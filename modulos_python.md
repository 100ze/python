```python

import <module_name> [, <module_name>]...

import <module_name> as <alternative_name>

from <module_name> import <module_name> [, <module_name>]...

from <module_name> import *

from <module_name> import <module_name> as <alternate_name> [, import <module_name> as <alternate_name>]...

import sys
print(sys.path)

import importlib
importlib.reload(imported_module)

# executado sempre que um pacote ou módulo dentro do pacote é importado
__init__.py

# todos os símbolos que começam com _ são ignorados quando importados, seja em um módulo ou pacote

# mesmo quando se usa "import *" o __init__.py é executado, e para que "import *" importe alguma coisa, os módulos ou pacotes devem estar listados em um array chamado __all__ dentro do arquivo __init__.py
from <package_name> import *
__init__.py << __all__ = ["<module_name" [, "<module_name>"]...]

# __all__ pode ser usado não apenas em __init__.py, mas em um módulo do qual se queira definir quais partes devem ser importadas

// pkg/modulo_1.py
__all__ = ["foo"]

def foo():
  print("foo")

# a classe Foo não será importada com:
# from pkg.modulo_1 import *
class Foo:
  pass

# cuidado: enquanto em um pacote sem __all__ nada é importado, em um módulo sem __all__ todos os símbolos serão importados (exceto os que comecem com _)

# em subpacotes pode ser usado o .. para acessar o pacote pai acima (precisa ter um pacote pai ou dará erro)
import ..pacote2
from .. import pacote2
```
