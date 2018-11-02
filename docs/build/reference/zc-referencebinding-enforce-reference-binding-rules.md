---
title: '/Zc: referencebinding (参照のバインディング ルールの適用)'
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: baf2106f015a4e8557cb8469d300709694e06d84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428328"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc: referencebinding (参照のバインディング ルールの適用)

ときに、 **/zc: referencebinding**オプションを指定すると、コンパイラが一時的にバインドする非定数の左辺値参照を許可しません。

## <a name="syntax"></a>構文

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Remarks

場合 **/zc: referencebinding**指定は、コンパイラが標準の c++ 11 の 8.5.3 に依存して、一時的なユーザー定義型を非定数の左辺値参照にバインドする式を許可しません。 既定では、場合 **/Zc:referenceBinding-** コンパイラは、Microsoft の拡張機能としては、このような式を使用できますが、レベル 4 の警告が発行されるを指定します。 コードのセキュリティ、移植性および適合性、お勧めを使用すること **/zc: referencebinding**します。

**/Zc: referencebinding**オプションは既定でオフです。 [/Permissive -](permissive-standards-conformance.md)コンパイラ オプションでは、このオプションは、暗黙的に設定しますを使用してオーバーライドできます **/Zc:referenceBinding-** します。

## <a name="example"></a>例

このサンプルでは、非定数の左辺値参照にバインドするには、ユーザー定義型の一時を許可する、Microsoft 拡張機能を示します。

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/zc: referencebinding**選び、 **OK**します。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
