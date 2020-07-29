---
title: vtordisp プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: a6ffc5c0323389d812e659ff68555a8c8c993126
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219366"
---
# <a name="vtordisp-pragma"></a>vtordisp プラグマ

**C++ 固有の仕様**

非表示の構築/破棄のディスプレイスメントメンバーの追加を制御し `vtordisp` ます。

## <a name="syntax"></a>構文

> **#pragma vtordisp (** [**プッシュ,** ] *n* **)**\
> **#pragma vtordisp (pop)**\
> **#pragma vtordisp ()**\
> **#pragma vtordisp (** [**プッシュ,** ] { **on**  |  **off** } **)**

### <a name="parameters"></a>パラメーター

**押し付け**\
現在の `vtordisp` 設定を内部コンパイラスタックにプッシュし、新しい `vtordisp` 設定を*n*に設定します。  *N*が指定されていない場合、現在の `vtordisp` 設定は変更されません。

**ショート**\
内部コンパイラスタックから上位レコードを削除し、 `vtordisp` 削除された値に設定を復元します。

*非該当*\
設定の新しい値を指定し `vtordisp` ます。 使用可能な値は `/vd0` 、、 `/vd1` 、およびコンパイラオプションに対応する0、1、または2です `/vd2` 。 詳細については、「 [/vd (コンストラクションの変位の無効化)](../build/reference/vd-disable-construction-displacements.md)」を参照してください。

**代わっ**\
`#pragma vtordisp(1)` と同等です。

**オート**\
`#pragma vtordisp(0)` と同等です。

## <a name="remarks"></a>解説

**Vtordisp**プラグマは、仮想ベースを使用するコードにのみ適用できます。 派生クラスが仮想基底クラスから継承する仮想関数をオーバーライドする場合、および派生クラスのコンストラクターやデストラクターが仮想基底クラスへのポインターを使用してその関数を呼び出す場合、コンパイラは仮想基底クラスを含むクラスに追加の `vtordisp` 隠しフィールドを導入する場合があります。

**Vtordisp**プラグマは、その後に続くクラスのレイアウトに影響します。 、、およびの各オプションでは、 `/vd0` `/vd1` `/vd2` モジュール全体で同じ動作を指定します。 0または**off**を指定すると、非表示のメンバーが抑制さ `vtordisp` れます。 クラスのコンストラクターとデストラクターがポインターによって指されたオブジェクトの仮想関数を呼び出す可能性がない場合にのみ、 **vtordisp**をオフにし **`this`** ます。

1または**on**(既定値) を指定すると、必要に応じて非表示のメンバーが有効になり `vtordisp` ます。

2を指定する `vtordisp` と、仮想関数を持つすべての仮想ベースに対して非表示のメンバーが有効になります。  `#pragma vtordisp(2)`は **`dynamic_cast`** 、部分的に構築されたオブジェクトでののパフォーマンスを適切に確保するために必要になる場合があります。 詳細については、「[コンパイラの警告 (レベル 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)」を参照してください。

`#pragma vtordisp()`引数を指定せずに、 `vtordisp` 設定を初期設定に戻します。

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
