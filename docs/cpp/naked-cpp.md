---
description: '詳細情報: 生 (C++)'
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: 1f416f116d7d2a3179dc43545f1302fcd9c7d101
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313828"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft 固有の仕様**

属性を使用して宣言された関数の場合 **`naked`** 、コンパイラはプロローグコードとエピローグコードを含まないコードを生成します。 この機能を使用して、プロローグとエピローグのコード シーケンスをインライン アセンブラー コードで独自に記述できます。 naked 関数は、仮想デバイス ドライバーの記述用に特に便利です。  **`naked`** 属性は x86 と ARM でのみ有効であり、x64 では使用できないことに注意してください。

## <a name="syntax"></a>構文

```
__declspec(naked) declarator
```

## <a name="remarks"></a>解説

属性は **`naked`** 関数の定義だけに関連し、型修飾子ではないため、生の関数では拡張属性構文と [__declspec](../cpp/declspec.md) キーワードを使用する必要があります。

関数が [__forceinline](inline-functions-cpp.md) キーワードでマークされている場合でも、コンパイラは、生の属性でマークされた関数のインライン関数を生成できません。

**`naked`** 非メンバーメソッドの定義以外に属性が適用されると、コンパイラはエラーを発行します。

## <a name="examples"></a>例

このコードは、属性を持つ関数を定義し **`naked`** ます。

```
__declspec( naked ) int func( formal_parameters ) {}
```

または、次のようにします。

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

属性は、 **`naked`** 関数のプロローグとエピローグのシーケンスに対するコンパイラのコード生成の性質にのみ影響します。 このような関数を呼び出すために生成されるコードには影響を与えません。 したがって、 **`naked`** 属性は関数の型の一部とは見なされず、関数ポインターは属性を持つことができません **`naked`** 。 さらに、 **`naked`** 属性をデータ定義に適用することはできません。 たとえば、次のサンプル コードはエラーになります。

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**`naked`** 属性は関数の定義にのみ関連し、関数のプロトタイプでは指定できません。 たとえば、次の宣言はコンパイラ エラーになります。

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[生の関数呼び出し](../cpp/naked-function-calls.md)
