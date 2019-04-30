---
title: conform
ms.date: 11/04/2016
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 35c3b06106779a9056f682ff76c6ed4b4ab1ab41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366760"
---
# <a name="conform"></a>conform
**C++ 固有の仕様**

実行時の動作を指定します、 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラ オプション。

## <a name="syntax"></a>構文

> **#pragma conform(** *name* **[, show]** [**,** { **on** | **off** } ] [ [**,** { **push** | **pop** } ] [**,** *identifier* ] ] **)**

### <a name="parameters"></a>パラメーター

*name*<br/>
変更されるコンパイラ オプションの名前を指定します。 唯一の有効な*名前*は`forScope`します。

**show**<br/>
(省略可能)現在の設定と、*名前*(true または false)、コンパイル時に警告メッセージとして表示されます。 たとえば、`#pragma conform(forScope, show)` のようにします。

**で**、**オフ**<br/>
(省略可能)設定*名前*に**で**により、 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラ オプション。 既定値は**オフ**します。

**push**<br/>
(省略可能)現在の値をプッシュ*名前*内部コンパイラ スタックにします。 指定する場合*識別子*を指定できます、**で**または**オフ**値*名前*をスタックにプッシュします。 たとえば、`#pragma conform(forScope, push, myname, on)` のようにします。

**pop**<br/>
(省略可能)値を設定*名前*を内部コンパイラ スタックと、pop、スタックの上部にある値。 識別子を指定した場合**pop**、レコードが見つかるまで戻るスタックがポップされます*識別子*、これもポップされます; の現在の値*名前*でスタック上の次のレコードの新しい値になります*名前*します。 指定した場合**pop**で、*識別子*スタックで、レコード内でない、 **pop**は無視されます。

*identifier*<br/>
(省略可能)含めることができます、**プッシュ**または**pop**コマンド。 場合*識別子*を使用する、**で**または**オフ**指定子も使用できます。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)