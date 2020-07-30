---
title: /Zc:strictStrings (文字列リテラル型の変換の無効化)
ms.date: 03/06/2018
f1_keywords:
- /Zc:strictStrings
- strictStrings
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
ms.openlocfilehash: df880ed64fa472ff55eb5ee0d17caacf56228ab6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211893"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>`/Zc:strictStrings`(文字列リテラル型の変換を無効にします)

指定した場合、コンパイラは、 **`const`** 文字列リテラルを使用して初期化されたポインターに対して厳密修飾準拠を必要とします。

## <a name="syntax"></a>構文

> **`/Zc:strictStrings`**[**`-`**]

## <a name="remarks"></a>解説

を指定した場合、 **`/Zc:strictStrings`** コンパイラは、 **`const`** 宣言に応じて、文字列リテラルの標準 C++ の修飾を、型 ' 配列 ' または ' 配列 ' の型として適用し `const char` `const wchar_t` ます。 文字列リテラルは変更不可であり、文字列リテラルの内容を変更しようとすると、実行時にアクセス違反エラーが発生します。 文字列ポインターをとして宣言して **`const`** 文字列リテラルを使用して初期化するか、明示的なを使用して **`const_cast`** 非ポインターを初期化する必要があり **`const`** ます。 既定では、またはが指定されている場合、コンパイラは、 **`/Zc:strictStrings-`** **`const`** 文字列リテラルを使用して初期化された文字列ポインターに標準 C++ の修飾を強制しません。

**`/Zc:strictStrings`** 既定では、このオプションはオフになっています。 [`/permissive-`](permissive-standards-conformance.md)コンパイラオプションはこのオプションを暗黙的に設定しますが、を使用してオーバーライドすることもでき **`/Zc:strictStrings-`** ます。

オプションを使用して、 **`/Zc:strictStrings`** 不適切なコードをコンパイルしないようにします。 この例では、単純な宣言エラーが実行時のクラッシュを招くことを示しています。

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

を有効にすると、 **`/Zc:strictStrings`** 同じコードによっての宣言でエラーが報告され `str` ます。

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

を使用して文字列ポインターを宣言する場合、 **`auto`** コンパイラは正しい **`const`** ポインター型宣言を作成します。 ポインターの内容を変更しようとすると、 **`const`** コンパイラによってエラーとして報告されます。

> [!NOTE]
> Visual Studio 2013 の C++ 標準ライブラリでは、 **`/Zc:strictStrings`** デバッグビルドのコンパイラオプションはサポートされていません。 ビルド出力に複数の[C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md)エラーが表示される場合は、これが原因である可能性があります。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. を含めるように "**追加オプション**" プロパティを変更し、[ **`/Zc:strictStrings`** **OK]** を選択します。

## <a name="see-also"></a>関連項目

[`/Zc`互換性](zc-conformance.md)<br/>
