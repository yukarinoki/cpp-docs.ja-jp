---
description: '詳細情報: 最適化 pragma'
title: 最適化 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragma, optimize
- optimize pragma
no-loc:
- pragma
ms.openlocfilehash: d9044788d0eea394867622d0f7aea1e365ad3399
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713455"
---
# <a name="optimize-no-locpragma"></a>`optimize` pragma

関数ごとの最適化を指定します。

## <a name="syntax"></a>構文

> **`#pragma optimize( "`** [ *最適化-リスト* ] **`",`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>解説

は **`optimize`** pragma 関数の外に置く必要があります。 は、が表示された後に定義された最初の関数で有効になり pragma ます。 **`on`** 引数と **`off`** 引数は、*最適化リスト* に指定されているオプションを有効または無効にします。

*最適化リスト* には、次の表に示すパラメーターの0個以上を指定できます。

### <a name="parameters-of-the-optimize-pragma"></a>optimize プラグマのパラメーター

| パラメーター | 最適化の種類 |
|--------------------|--------------------------|
| **`g`** | グローバル最適化を有効にします。 |
| **`s`** または **`t`** | マシン語コードの省略シーケンスまたは高速シーケンスを指定します。 |
| **`y`** | プログラム スタックにフレーム ポインターを生成します。 |

これらのパラメーターは、コンパイラオプションで使用される文字と同じ [`/O`](../build/reference/o-options-optimize-code.md) です。 たとえば、次の例 pragma はコンパイラオプションに相当し **`/Os`** ます。

```cpp
#pragma optimize( "s", on )
```

を **`optimize`** pragma 空の文字列 () と共に使用すること **`""`** は、ディレクティブの特殊な形式です。

パラメーターを使用すると、すべての最適化、、、 **`off`** **`g`** 、およびがオフになり **`s`** **`t`** **`y`** ます。

パラメーターを使用すると、 **`on`** コンパイラオプションを使用して指定した最適化がリセットされ [`/O`](../build/reference/o-options-optimize-code.md) ます。

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
