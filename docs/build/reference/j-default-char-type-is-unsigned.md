---
description: 詳細情報:/J (既定の char 型は符号なし)
title: /J (既定の char 型の unsigned への変更)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: 0e6f09a05925fd0248f1e777d578570cd7b44946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191226"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (既定の char 型の unsigned への変更)

既定の **`char`** 型をから **`signed char`** に変更 **`unsigned char`** します。型が **`char`** 型に拡張されると、型はゼロ拡張され **`int`** ます。

## <a name="syntax"></a>構文

```
/J
```

## <a name="remarks"></a>解説

**`char`** 値がとして明示的に宣言されている場合 **`signed`** 、 **/j** オプションはそれに影響しません。値は、型に拡張されたときに符号拡張され **`int`** ます。

**/J** オプションはを定義し `_CHAR_UNSIGNED` ます。これは、 `#ifndef` 既定の型の範囲を定義するために、制限 .h ファイルのと共に使用されます。 **`char`**

ANSI C と C++ では、型の特定の実装は必要ありません **`char`** 。 このオプションは、文字データを操作していて、最終的には英語以外の言語に変換される場合に便利です。

> [!NOTE]
> ATL/MFC でこのコンパイラオプションを使用すると、エラーが生成される場合があります。 を定義することでこのエラーを無効にすることもでき `_ATL_ALLOW_CHAR_UNSIGNED` ますが、この回避策はサポートされていないため、常に機能するとは限りません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. **ソリューション エクスプローラー** で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. [プロジェクト **プロパティページ** ] ダイアログボックスの左側のウィンドウで、 **[構成プロパティ**] の下の [ **C/c + +** ] を展開し、[ **コマンドライン**] を選択します。

1. [ **追加オプション** ] ウィンドウで、 **/j** コンパイラオプションを指定します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)
