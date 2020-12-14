---
description: /V (バージョン番号) の詳細情報
title: /V (バージョン番号)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 5025642d4ae30315d24754a7ee46268050cfb22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187053"
---
# <a name="v-version-number"></a>/V (バージョン番号)

非推奨になりました。 .Obj ファイルにテキスト文字列を埋め込みます。

## <a name="syntax"></a>構文

```
/Vstring
```

## <a name="arguments"></a>引数

*string*<br/>
.Obj ファイルに埋め込まれるバージョン番号または著作権表記を指定する文字列。

## <a name="remarks"></a>解説

Stringcan には、バージョン番号または著作権に関する通知を付けることができます。 文字列の一部である場合は、スペースまたはタブ文字を二重引用符 (") で囲む必要があります。 バックスラッシュ ( \\ ) は、文字列の一部である場合は、二重引用符の前に付ける必要があります。 **/V** との間のスペース `string` は省略可能です。

また、 [comment (C/c + +)](../../preprocessor/comment-c-cpp.md) をコンパイラのコメント型引数と共に使用して、コンパイラの名前とバージョン番号を .obj ファイルに配置することもできます。

**/V** オプションは、Visual Studio 2005 以降では非推奨とされます。**/V** は、主に仮想デバイスドライバー (vxd) の構築をサポートするために使用され、Visual C++ ツールセットではビルド vxd はサポートされなくなりました。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
