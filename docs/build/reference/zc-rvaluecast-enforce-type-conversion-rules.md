---
title: /Zc:rvalueCast (型変換規則の適用)
ms.date: 03/06/2018
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: e5a6abd3b85136b05ae58ebc8750aa9120cabc33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315782"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (型変換規則の適用)

ときに、 **/Zc:rvalueCast**オプションを指定すると、コンパイラは、c++ 11 標準に従いキャスト操作の結果として右辺値参照型を正しく識別します。 このオプションを指定しない場合、コンパイラの動作は Visual Studio 2012 での動作と同じです。

## <a name="syntax"></a>構文

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>Remarks

場合 **/Zc:rvalueCast**指定するコンパイラが標準の c++ 11 のセクション 5.4 をに従ってし、キャスト非参照型の結果を関数ではない型への右辺値参照になる式をキャスト式のみを扱い、右辺値の型。 既定では、場合 **/Zc:rvalueCast-** 指定は、コンパイラは非準拠と右辺値として右辺値参照になるすべてのキャスト式を処理します。 使用することをお勧め標準に準拠しエラー キャストの使用を排除する **/Zc:rvalueCast**します。

既定では、 **/Zc:rvalueCast**がオフ (**/Zc:rvalueCast-**)。 [/Permissive -](permissive-standards-conformance.md)コンパイラ オプションでは、このオプションは、暗黙的に設定しますを使用してオーバーライドできます **/Zc:rvalueCast-** します。

使用 **/Zc:rvalueCast**キャスト式を右辺値参照型を受け取る関数に引数として渡す場合。 既定の動作は、コンパイラ エラーを発生[C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)ときに、コンパイラ誤って判断キャスト式の型。 この例では、コンパイラ エラーを示しますで適切なときにコード **/Zc:rvalueCast**が指定されていません。

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

コンパイラの既定動作では、場合によっては C2102 エラーが報告されないことがあります。 この例で、コンパイラはエラーを報告しません、id のキャストによって作成された右辺値のアドレスが作成された場合 **/Zc:rvalueCast**が指定されていません。

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:rvalueCast**選び、 **OK**します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
