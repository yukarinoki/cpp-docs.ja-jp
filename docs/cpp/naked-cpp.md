---
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: cfe3631086515e4e31c7d4188d46e3a7440662b7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177951"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft 固有の仕様**

**生**の属性を使用して宣言された関数の場合、コンパイラはプロローグコードとエピローグコードを含まないコードを生成します。 この機能を使用して、プロローグとエピローグのコード シーケンスをインライン アセンブラー コードで独自に記述できます。 naked 関数は、仮想デバイス ドライバーの記述用に特に便利です。  **生**の属性は X86 と ARM でのみ有効であり、x64 では使用できないことに注意してください。

## <a name="syntax"></a>構文

```
__declspec(naked) declarator
```

## <a name="remarks"></a>解説

**生**の属性は関数の定義のみに関連し、型修飾子ではないため、生の関数では拡張属性構文と[__declspec](../cpp/declspec.md)キーワードを使用する必要があります。

関数が[__forceinline](inline-functions-cpp.md)キーワードでマークされている場合でも、コンパイラは、生の属性でマークされた関数のインライン関数を生成できません。

非メンバーメソッドの定義以外に**生**の属性が適用されると、コンパイラはエラーを発行します。

## <a name="examples"></a>例

このコードは、次のように、**生**の属性を持つ関数を定義します。

```
__declspec( naked ) int func( formal_parameters ) {}
```

または、次のようにします。

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

**生**の属性は、関数のプロローグとエピローグのシーケンスに対するコンパイラのコード生成の性質にのみ影響します。 このような関数を呼び出すために生成されるコードには影響を与えません。 したがって、**生**の属性は関数の型の一部とは見なされず、関数ポインターは**生**の属性を持つことができません。 さらに、**生**の属性をデータ定義に適用することはできません。 たとえば、次のサンプル コードはエラーになります。

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**生**の属性は関数の定義にのみ関連し、関数のプロトタイプでは指定できません。 たとえば、次の宣言はコンパイラ エラーになります。

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[naked 関数呼び出し](../cpp/naked-function-calls.md)
