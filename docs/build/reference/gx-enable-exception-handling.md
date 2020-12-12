---
description: 詳細情報:/GX (例外処理の有効化)
title: /GX (例外処理の有効化)
ms.date: 11/19/2019
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: e511407504129f94b615fb3ec05c9f8a04766b10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191707"
---
# <a name="gx-enable-exception-handling"></a>/GX (例外処理の有効化)

非推奨になりました。 を使用して宣言された関数が例外をスローしないことを想定して、同期例外処理を有効にし `extern "C"` ます。

## <a name="syntax"></a>構文

```
/GX
```

## <a name="remarks"></a>解説

**/Gx** は非推奨とされます。 代わりに、 [/ehsc](eh-exception-handling-model.md) オプションを使用してください。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別のコンパイラオプション](compiler-options-listed-by-category.md)」の「**非推奨のコンパイラオプション**」セクションを参照してください。

既定では、 **/ehsc** は **/gx** に相当しますが、Visual Studio 開発環境を使用してコンパイルすると有効になります。 コマンドラインツールを使用する場合、例外処理は指定されません。 これは、 **/GX-** に相当します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. ナビゲーションウィンドウで、[ **構成プロパティ**]、[ **C/c + +**]、[ **コマンドライン**] の順に選択します。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/EH (例外処理モデル)](eh-exception-handling-model.md)
