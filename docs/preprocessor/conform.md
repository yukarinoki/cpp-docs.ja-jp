---
description: '詳細情報: 準拠プラグマ'
title: conform プラグマ
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: bb9f62194196ea32e5f3326116894ea56ef83611
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300763"
---
# <a name="conform-pragma"></a>conform プラグマ

**C++ 固有の仕様**

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラオプションの実行時の動作を指定します。

## <a name="syntax"></a>構文

> **#pragma 準拠** している (*名前*[ **, show** ] [ **,** { **on**  |  **off** }] [[ **,** { **push**  |  **pop** }] [ **,** *identifier* [ **,** { **on**  |  **off** }]] **)**

### <a name="parameters"></a>パラメーター

*指定*\
変更されるコンパイラ オプションの名前を指定します。 有効な *名前* はだけです `forScope` 。

**示**\
Optional *名前* の現在の設定 (true または false) を、コンパイル中に警告メッセージで表示します。 たとえば、「 `#pragma conform(forScope, show)` 」のように入力します。

**on**、 **off**\
Optional *名前* を **on** に設定すると、 [/zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) コンパイラオプションが有効になります。 既定値は **off** です。

**押し付け**\
Optional *名前* の現在の値を内部コンパイラスタックにプッシュします。 *識別子* を指定すると、スタックにプッシュされる *名前* の **on** または **off** の値を指定できます。 たとえば、「 `#pragma conform(forScope, push, myname, on)` 」のように入力します。

**ショート**\
Optional *Name* の値を内部コンパイラスタックの一番上の値に設定し、スタックをポップします。 識別子を **pop** と共に指定すると、 *識別子* を持つレコードが見つかるまでスタックがポップされます。これもポップされます。スタック上の次のレコードの [ *名前* ] の現在の値が、[ *名前*] の新しい値になります。 スタック上のレコードに含まれていない *識別子* を使用して **pop** を指定すると、 **pop** は無視されます。

*identifier*\
Optional **プッシュ** または **pop** コマンドに含めることができます。 *識別子* を使用する場合は、 **on** または **off** 指定子も使用できます。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
