# Guia de Nomenclatura – Dart/Flutter

**Baseado no Clean Code – Uncle Bob**

Este guia define práticas de nomenclatura para manter **clareza, consistência e legibilidade** em todo o projeto Dart/Flutter.

---

## 🎯 Princípios Gerais

* **Intenção clara**: o nome deve revelar **o que é** e **para que serve**.
* **Do específico → genérico**: descreva primeiro a intenção e depois o tipo.

  * ✅ `EditarParcelaDialog`
  * ❌ `DialogEditarParcela`
* **Consistência**: use sempre o mesmo padrão em todo o código.
* **Evite ruído**: palavras como `Manager`, `Helper`, `Processor` são inúteis.
* **Evite abreviações**: prefira `parcela` a `prc`.
* **Profissionalismo**: nomes não devem ser piadas, memes ou gírias.
* **Pronunciáveis**: nomes devem ser fáceis de ler em voz alta.
* **Pesquisar é fácil**: valores mágicos e números soltos devem ter nome descritivo.

---

## 📂 Arquivos

* Nome do arquivo = **nome da classe principal** (mesmo casing adaptado).
* Use **snake\_case** nos arquivos.
* Exemplos:

  * ✅ `editar_parcela_dialog.dart`
  * ✅ `parcela_service.dart`
  * ❌ `EditarParcelaDialog.dart`
  * ❌ `dialog_editar_parcela.dart`

---

## 🏷️ Classes

* Nome em **PascalCase**.
* Devem ser **substantivos** ou **substantivo + propósito**.
* Exemplos:

  * ✅ `UsuarioRepository`, `ParcelaService`, `EditarParcelaDialog`
  * ❌ `DoStuff`, `ClasseManager`, `DataHandler`

---

## 🔧 Métodos / Funções

* Nome em **camelCase**.
* Devem ser **verbos ou frases verbais** (ação).
* Exemplos:

  * ✅ `calcularTotal()`, `buscarParcelas()`, `showDialogEditarParcela()`
  * ❌ `total()`, `doCalculation()`, `handleData()`
* **Exceção**: funções que retornam algo imutável podem ser substantivos curtos: `now()`, `usuario()`.

---

## 🧩 Variáveis e Propriedades

* Nome em **camelCase**.
* Devem ser **descritivas** → nada de `tmp`, `obj`, `x` sem contexto.
* Exemplos:

  * ✅ `nomeUsuario`, `listaParcelas`, `valorTotal`
  * ❌ `nmUsr`, `list1`, `valor`

---

## ✅ Booleanos

* Use prefixos que deixem explícito que é **booleano**:

  * `is...` → estado verdadeiro/falso
  * `has...` → existência/posse
  * `can...` → capacidade/permissão
  * `should...` → decisão/recomendação

### Exemplos bons:

```dart
bool isValid;
bool isEmpty;
bool hasError;
bool canRetry;
bool shouldRefresh;
```

### Exemplos ruins:

```dart
bool valido;       // pouco claro que é booleano
bool validBool;    // redundante
bool isValidFlag;  // sufixo "Flag" é ruído
```

📌 **Regra prática:** a variável booleana deve poder ser lida como uma frase verdadeira/falsa:

```dart
if (parcela.isValid) ...
if (usuario.hasPermission) ...
if (cache.shouldRefresh) ...
```

---

## 🧾 Constantes

* Nome em **camelCase** se for `const` local/privado.
* Nome em **SCREAMING\_SNAKE\_CASE** se for `const` pública.
* Exemplos:

  * ✅ `const margemPadrao = 16.0;`
  * ✅ `const API_BASE_URL = "https://api.exemplo.com";`

---

## 🎨 Widgets (Flutter)

* Nome em **PascalCase**.
* Ordem: **Intenção + Tipo**.
* Exemplos:

  * ✅ `LoginForm`, `UsuarioCard`, `EditarParcelaDialog`, `TrocarMesButton`
  * ❌ `FormLogin`, `CardUsuario`, `DialogEditarParcela`, `ButtonTrocarMes`

---

## 💬 Dialogs / Modais

* Widget: `EditarParcelaDialog`
* Função de exibição: `showDialogEditarParcela(context, ...)`
* Segue padrão do Flutter (`showDatePicker`, `showTimePicker`).

---

## 📦 Pastas

* Use **snake\_case**.
* Nomeie pastas pelo **domínio/contexto**, não pelo tipo genérico.
* Exemplos:

  * ✅ `parcelas/`, `autenticacao/`, `produtos/`
  * ❌ `utils/`, `helpers/`, `common/`

---

## 🧠 Outras boas práticas (Uncle Bob)

* **Evite palavras vazias**: não use `Manager`, `Helper`, `Processor`, `Info`, `Data`.
* **Evite nomes duplicados**: um mesmo nome não pode significar coisas diferentes.
* **Evite piadas ou gírias**: nomes devem ser profissionais.
* **Nomes pronunciáveis**: prefira `nomeUsuario` a `nmUsr`.
* **Nomes pesquisáveis**: evite números mágicos ou variáveis sem nome.
* **Nomes curtos vs longos**: quanto maior o escopo, mais descritivo deve ser o nome.
* **Evite codificação mental**: nada de `mNome`, `szLista`.
* **Consistência de vocabulário**: escolha termos e use sempre os mesmos (`buscar`, `calcular`, `atualizar`).

---

## ✅ Resumão

| Tipo              | Convenção              | Exemplo Bom                  | Exemplo Ruim               |
| ----------------- | ---------------------- | ---------------------------- | -------------------------- |
| Classe / Widget   | PascalCase             | `EditarParcelaDialog`        | `DialogEditarParcela`      |
| Função / Método   | camelCase              | `buscarParcelas()`           | `getParcels()`             |
| Variável          | camelCase              | `valorTotal`                 | `vTotal`                   |
| Booleano          | is/has/can/should      | `isValid`                    | `isValidFlag`              |
| Constante pública | SCREAMING\_SNAKE\_CASE | `API_BASE_URL`               | `apiBaseUrl`               |
| Constante local   | camelCase              | `margemPadrao`               | `MARGEM_PADRAO`            |
| Arquivo           | snake\_case            | `editar_parcela_dialog.dart` | `EditarParcelaDialog.dart` |
| Pasta             | snake\_case            | `autenticacao/`              | `helpers/`                 |

---
