---
title: C 文字列リテラル | Microsoft Docs
ms.custom: ''
ms.date: 08/31/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57bd79e1df35f650d78da3108137d58405b33f25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082015"
---
# <a name="c-string-literals"></a>C 文字列リテラル

"文字列リテラル" は、二重引用符 (**" "**) で囲まれたソース文字セットの文字のシーケンスです。 文字列リテラルは、まとめて扱われる、null で終わる文字列を形成する文字のシーケンスを表すために使用されます。 ワイド文字列リテラルの前には、常に文字 **L** を付ける必要があります。

## <a name="syntax"></a>構文

*string-literal*: &nbsp;&nbsp;&nbsp;&nbsp;**"** *s-char-sequence*<sub>opt</sub> **"** &nbsp;&nbsp;&nbsp;&nbsp;**L"** *s-char-sequence*<sub>opt</sub> **"**

*s-char-sequence*: &nbsp;&nbsp;&nbsp;&nbsp;*s-char* &nbsp;&nbsp;&nbsp;&nbsp;*s-char-sequence* *s-char*

*s-char*: &nbsp;&nbsp;&nbsp;&nbsp;二重引用符 (")、円記号 (\\)、または改行文字 &nbsp;&nbsp;&nbsp;&nbsp;*エスケープ シーケンス*を除くソース文字セットのメンバー

## <a name="remarks"></a>コメント

次の例は、単純な文字列リテラルです。

```C
char *amessage = "This is a string literal.";
```

「[エスケープ シーケンス](../c-language/escape-sequences.md)」テーブルに示されたすべてのエスケープ コードは、文字列リテラルで有効です。 文字列リテラル内で二重引用符を表すには、エスケープ シーケンス **\\"** を使用します。 単一引用符 (**'**) は、エスケープ シーケンスを使用せずに表すことができます。 円記号 (**\\**) を文字列内で使用する場合は、直後に 2 つ目の円記号を付ける (**\\\\**) 必要があります。 行の末尾にあるバックスラッシュは、常に行連結文字として解釈されます。

## <a name="see-also"></a>参照

[C の要素](../c-language/elements-of-c.md)
