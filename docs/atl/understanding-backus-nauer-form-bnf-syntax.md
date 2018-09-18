---
title: ATL レジストラーとバッカスナウア記法 (BNF) 構文が形成されます |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e615068580bcc9078959cc6cdd7831d05b5a4acd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020876"
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>バッカスナウア記法 (Bnf) 構文を理解します。

ATL レジストラーで使用されるスクリプトは、BNF 構文は、次の表に示すように表記を使用してを使用して、このトピックで説明します。

|規則/シンボル|説明|
|------------------------|-------------|
|::=|同等の表記|
|&#124;|OR|
|X +|1 つまたは複数の Xs します。|
|[X]|X は省略可能です。 省略可能な区切り記号が付いた\[]。|
|すべて**太字**テキスト|リテラル文字列。|
|すべて*斜体*テキスト|文字列リテラルを作成する方法。|

上記の表に示されるように、レジストラー スクリプトは、文字列リテラルを使用します。 これらの値は、実際のテキストをスクリプトに表示する必要があります。 次の表には、ATL レジストラー スクリプトで使用される文字列リテラルがについて説明します。

|文字列リテラル|アクション|
|--------------------|------------|
|**ForceRemove**|(存在する) 場合、次のキーを完全に削除してから再作成します。|
|**NoRemove**|登録解除中には、次のキーは削除されません。|
|**val**|指定します`<Key Name>`は実際には名前付きの値です。|
|**削除**|登録中に次のキーを削除します。|
|**s**|[次へ] の値が文字列 (REG_SZ) であることを指定します。|
|**d**|[次へ] の値が DWORD (REG_DWORD) であることを指定します。|
|**m**|[次へ] の値が複数文字列 (REG_MULTI_SZ) であることを指定します。|
|**b**|[次へ] の値がバイナリ値 (REG_BINARY) であることを指定します。|

## <a name="bnf-syntax-examples"></a>BNF 構文例

ATL レジストラー スクリプトで表記と文字列リテラルのしくみを理解するためのいくつかの構文例を示します。

### <a name="syntax-example-1"></a>構文の例 1

```
<registry expression> ::= <Add Key>
```

指定します`registry expression`と等価`Add Key`します。

### <a name="syntax-example-2"></a>構文例 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

指定します`registry expression`はいずれかに相当`Add Key`または`Delete Key`します。

### <a name="syntax-example-3"></a>構文例 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

指定します`Key Name`は 1 つ以上に相当`AlphaNumerics`します。

### <a name="syntax-example-4"></a>構文例 4

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

指定します`Add Key`と等価`Key Name`、および、文字列リテラル`ForceRemove`、 `NoRemove`、および`val`は省略可能です。

### <a name="syntax-example-5"></a>構文例 5

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

指定します`AlphaNumeric`を NULL 以外の文字と同じです。

### <a name="syntax-example-6"></a>構文例 6

```
val 'testmulti' = m 'String 1\0String 2\0'
```

指定します、キー名`testmulti`が複数行文字列の値から成る`String 1`と`String 2`します。

### <a name="syntax-example-7"></a>構文例 7

```
val 'testhex' = d '&H55'
```

指定します、キー名`testhex`DWORD 値は 16 進数の 55 (10 進 85) に設定されます。 この形式に準拠するメモ、 **& H**として表記、Visual Basic 仕様に記載します。

## <a name="see-also"></a>関連項目

[レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

