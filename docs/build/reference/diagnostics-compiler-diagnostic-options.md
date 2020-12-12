---
description: 詳細情報:/診断 (コンパイラ診断オプション)
title: /診断 (コンパイラの診断オプション)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 2c34edc0374e59720eb05e97379702833efaa703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201418"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/診断 (コンパイラの診断オプション)

**/Diagnostics** コンパイラオプションを使用して、エラーと警告の場所に関する情報の表示を指定します。

## <a name="syntax"></a>構文

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>解説

このオプションは、Visual Studio 2017 以降でサポートされています。

**/診断** コンパイラオプションは、エラーおよび警告情報の表示を制御します。

**/Diagnostics: classic** オプションは既定値であり、問題が見つかった行番号のみを報告します。

また、[ **診断: 列** ] オプションには、問題が見つかった列も含まれています。 これは、問題の原因となっている特定の言語構成要素または文字を識別するのに役立ちます。

**/Diagnostics: キャレット** オプションには、問題が検出された列が含まれ、問題が検出されたコード行の位置の下にキャレット (^) が配置されます。

場合によっては、コンパイラが発生した問題が検出されないことに注意してください。 たとえば、不足しているセミコロンは、他の予期しないシンボルが検出されるまで検出されない可能性があります。 列が報告され、問題が発生したことがコンパイラによって検出されたときにキャレットが配置されます。これは、必ずしも修正を行う必要がある場所ではありません。

**/診断** オプションは、Visual Studio 2017 以降で使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの [ **プロパティページ** ] ダイアログボックスを開きます。

1. [ **構成プロパティ**] で、[ **C/c + +** ] フォルダーを展開し、[ **全般** ] プロパティページをクリックします。

1. 診断の表示オプションを選択するには、[ **診断形式** ] フィールドのドロップダウンコントロールを使用します。 **[OK]** または [**適用**] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
