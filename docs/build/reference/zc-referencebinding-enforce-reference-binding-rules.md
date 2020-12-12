---
description: '詳細情報:/Zc: referenceBinding (参照バインド規則の適用)'
title: '/Zc: referenceBinding (参照のバインディング ルールの適用)'
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
ms.openlocfilehash: 7d094a2ec3ec680c463a7a756e70e02b9c40c07c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269160"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc: referenceBinding (参照のバインディング ルールの適用)

**/Zc: referenceBinding** オプションが指定されている場合、コンパイラは非定数の左辺値参照を一時にバインドすることを許可しません。

## <a name="syntax"></a>構文

> **/Zc: referenceBinding**[ **-** ]

## <a name="remarks"></a>解説

**/Zc: referenceBinding** が指定されている場合、コンパイラは c++ 11 標準のセクション8.5.3 に従います。これは、ユーザー定義型の一時を非定数の左辺値参照にバインドする式を許可しません。 既定では、 **/zc: referenceBinding-** が指定されている場合、コンパイラは Microsoft の拡張機能としてこのような式を許可しますが、レベル4の警告が発行されます。 コードセキュリティ、移植性、および準拠については、 **/zc: referenceBinding** を使用することをお勧めします。

**/Zc: referenceBinding** オプションは、既定ではオフになっています。 [/Permissive-](permissive-standards-conformance.md)コンパイラオプションは、暗黙的にこのオプションを設定しますが、 **/Zc: referencebinding-** を使用してオーバーライドできます。

## <a name="example"></a>例

このサンプルでは、非定数の左辺値参照にユーザー定義型の一時的なバインドを許可する Microsoft 拡張機能を示します。

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

int main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: referenceBinding** を含むように "**追加オプション**" プロパティを変更し、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Zc (準拠)](zc-conformance.md)<br/>
