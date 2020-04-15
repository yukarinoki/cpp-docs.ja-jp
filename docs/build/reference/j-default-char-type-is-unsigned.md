---
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
ms.openlocfilehash: 7bcf0f2eb2bef08757250999d0a6696b256fb15c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322195"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (既定の char 型の unsigned への変更)

`char`既定の`signed char`型を から`unsigned char`に変更`char`し、型が`int`拡張されると、その型は 0 拡張されます。

## <a name="syntax"></a>構文

```
/J
```

## <a name="remarks"></a>解説

として`char``signed`明示的に宣言されている場合 **、/J**オプションは`int`、その値に影響を与えません。

**/J**オプションは`_CHAR_UNSIGNED`、LIMITS.h`#ifndef`ファイルで使用`char`される 、 既定の型の範囲を定義するために定義します。

ANSI C および C++ では、型の`char`特定の実装は必要ありません。 このオプションは、最終的に英語以外の言語に翻訳される文字データを操作する場合に便利です。

> [!NOTE]
> ATL/MFC でこのコンパイラ オプションを使用すると、エラーが生成されることがあります。 このエラーを定義することで無効に`_ATL_ALLOW_CHAR_UNSIGNED`できますが、この回避策はサポートされておらず、常に機能するとは限りません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. **ソリューション エクスプローラ**で、プロジェクトのショートカット メニューを開き、[**プロパティ]** をクリックします。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスの左側のウィンドウで、[**構成プロパティ]** の下の **[C/C++]** を展開し、[**コマンド ライン**] を選択します。

1. [**追加オプション]** ペインで **、/J**コンパイラ オプションを指定します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)
