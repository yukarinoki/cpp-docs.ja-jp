---
description: Vtordisp の詳細については、「 pragma Microsoft C++」を参照してください。
title: vtordisp pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragma, vtordisp
- vtordisp pragma
no-loc:
- pragma
ms.openlocfilehash: f8956aa892aae0472001b007137e6f978d91500e
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713143"
---
# <a name="vtordisp-no-locpragma"></a>`vtordisp` pragma

非表示の構築/破棄のディスプレイスメントメンバーの追加を制御し `vtordisp` ます。 は `vtordisp` pragma C++ 固有です。

## <a name="syntax"></a>構文

> **`#pragma vtordisp(`**[ **`push,`** ] *n***`)`**\
> **`#pragma vtordisp(pop)`**\
> **`#pragma vtordisp()`**\
> **`#pragma vtordisp(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**

### <a name="parameters"></a>パラメーター

**`push`**\
現在の `vtordisp` 設定を内部コンパイラスタックにプッシュし、新しい `vtordisp` 設定を *n* に設定します。  *N* が指定されていない場合、現在の `vtordisp` 設定は変更されません。

**`pop`**\
内部コンパイラスタックから上位レコードを削除し、 `vtordisp` 削除された値に設定を復元します。

*非該当*\
設定の新しい値を指定し `vtordisp` ます。 使用できる値は、、、 **`0`** **`1`** **`2`** **`/vd0`** **`/vd1`** および **`/vd2`** コンパイラオプションに対応する、、またはです。 詳細については、「 [ `/vd` (コンストラクションの変位を無効にする)](../build/reference/vd-disable-construction-displacements.md)」を参照してください。

**`on`**\
これは、`#pragma vtordisp(1)` に相当します。

**`off`**\
これは、`#pragma vtordisp(0)` に相当します。

## <a name="remarks"></a>解説

は、 **`vtordisp`** pragma 仮想ベースを使用するコードにのみ適用できます。 派生クラスが仮想基底クラスから継承する仮想関数をオーバーライドし、派生クラスのコンストラクターまたはデストラクターが仮想基底クラスへのポインターを使用してその関数を呼び出す場合、コンパイラは仮想基底クラスを持つクラスに追加の非表示フィールドを導入することがあり `vtordisp` ます。

は、 **`vtordisp`** pragma その後に続くクラスのレイアウトに影響します。 **`/vd0`**、 **`/vd1`** 、および **`/vd2`** コンパイラオプションは、モジュール全体に対して同じ動作を指定します。 を指定する **`0`** か **`off`** 、非表示のメンバーを抑制し `vtordisp` ます。 **`vtordisp`** クラスのコンストラクターとデストラクターがポインターによって指されるオブジェクトの仮想関数を呼び出す可能性がない場合にのみ、をオフにし **`this`** ます。

またはを指定すると、 **`1`** **`on`** 既定では、必要に応じて非表示のメンバーが有効になり `vtordisp` ます。

を指定する **`2`** `vtordisp` と、仮想関数を持つすべての仮想ベースに対して非表示のメンバーが有効になります。 `#pragma vtordisp(2)` は **`dynamic_cast`** 、部分的に構築されたオブジェクトでののパフォーマンスを適切に確保するために必要になる場合があります。 詳細については、「 [コンパイラの警告 (レベル 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)」を参照してください。

`#pragma vtordisp()`引数を指定せずに、 `vtordisp` 設定を初期設定に戻します。

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
