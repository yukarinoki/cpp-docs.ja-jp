---
description: 詳細情報:/Fm (マップ名の名前を指定)
title: /Fm (マップ ファイルの名前の指定)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: 5c86a18ae9880a499997bcac2d8411859753d858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200482"
---
# <a name="fm-name-mapfile"></a>/Fm (マップ ファイルの名前の指定)

対応する .exe ファイルまたは DLL 内に出現する順序でセグメントの一覧を含む mapfile を生成するようにリンカーに指示します。

## <a name="syntax"></a>構文

```
/Fmpathname
```

## <a name="remarks"></a>解説

既定では、マップファイルには、対応する C または C++ ソースファイルのベース名が付きます。マップ拡張。

**/Fm** を指定すると、 [/map (Mapfile の生成)](map-generate-mapfile.md)リンカーオプションを指定した場合と同じ効果があります。

リンクを抑制するために [/c (リンクなしでコンパイル)](c-compile-without-linking.md) を指定した場合、 **/fm** は無効になります。

通常、マップ内のグローバルシンボルには、変数名に先頭にアンダースコアが追加されるため、1つまたは複数の先頭にアンダースコアが付いています。 Mapfile に表示される多くのグローバルシンボルは、コンパイラと標準ライブラリによって内部的に使用されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
