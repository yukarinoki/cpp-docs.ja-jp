---
description: pragmaMicrosoft C/c + + での準拠ディレクティブの詳細について説明します。
title: 従い pragma
ms.date: 01/22/2021
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragma, conform
no-loc:
- pragma
ms.openlocfilehash: baaeb41e2364daac8de91ca15251226bf3dd1e2a
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713702"
---
# <a name="conform-no-locpragma"></a>`conform` pragma

**C++ 固有の仕様**

コンパイラオプションの実行時の動作を指定し [`/Zc:forScope`](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) ます。

## <a name="syntax"></a>構文

> **`#pragma conform(`***名前*[ **`, show`** ] [ **`,`** { **`on`**  |  **`off`** }] [[ **`,`** { **`push`**  |  **`pop`** }] [ **`,`** *識別子*[ **`,`** { **`on`**  |  **`off`** }]]]**`)`**

### <a name="parameters"></a>パラメーター

*指定*\
変更されるコンパイラ オプションの名前を指定します。 有効な *名前* はだけです `forScope` 。

**`show`**\
Optional *名前* の現在の設定 (true または false) を、コンパイル中に警告メッセージで表示します。 たとえば、「 `#pragma conform(forScope, show)` 」のように入力します。

**`on`**, **`off`**\
Optional *名前* をに設定すると **`on`** 、 [/zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) コンパイラオプションが有効になります。 既定値は **`off`** です。

**`push`**\
Optional *名前* の現在の値を内部コンパイラスタックにプッシュします。 *識別子* を指定する場合は、スタックに **`on`** **`off`** プッシュされる *名前* の値または値を指定できます。 たとえば、「 `#pragma conform(forScope, push, myname, on)` 」のように入力します。

**`pop`**\
Optional *Name* の値を内部コンパイラスタックの一番上の値に設定し、スタックをポップします。 識別子がで指定されている場合 **`pop`** 、 *識別子* を持つレコードが見つかるまでスタックはポップバックされます。これもポップされます。スタック上の次のレコードの *名前* の現在の値は、 *name* の新しい値になります。 **`pop`** スタック上のレコードに含まれていない *識別子* を使用してを指定した場合、 **`pop`** は無視されます。

*identifier*\
Optionalは、コマンドまたはコマンドに含めることができ **`push`** **`pop`** ます。 *識別子* を使用する場合は、 **`on`** または **`off`** 指定子を使用することもできます。

## <a name="example"></a>例

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
