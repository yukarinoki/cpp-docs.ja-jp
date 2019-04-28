---
title: /VERBOSE (進行状況メッセージの出力)
ms.date: 11/04/2016
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
ms.openlocfilehash: 7aed1e17034b40ffdad4da4136fc5a64361b3d77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317303"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (進行状況メッセージの出力)

```
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]
```

## <a name="remarks"></a>Remarks

リンカーへのリンクのセッションの進行状況に関する情報を送信する、**出力**ウィンドウ。 コマンド ラインでリンクを実行すると、この情報は標準出力に送られるため、ファイルにリダイレクトできます。

|オプション|説明|
|------------|-----------------|
|/VERBOSE|リンク プロセスに関する詳細情報を表示します。|
|/VERBOSE:ICF|使用に起因するリンカー動作についての情報を表示[/OPT:ICF](opt-optimizations.md)します。|
|/VERBOSE:INCR|インクリメンタル リンク プロセスに関する情報を表示します。|
|/VERBOSE:LIB|検索されたライブラリだけを示す進行状況メッセージを表示します。<br /><br /> 表示される情報は、ライブラリ検索の進行状況、各ライブラリとオブジェクト名 (完全パス)、そのライブラリで解決されたシンボル、およびそのシンボルを参照しているオブジェクトの一覧です。|
|/VERBOSE:REF|使用に起因するリンカー動作についての情報が表示されます[/OPT:REF](opt-optimizations.md)します。|
|/VERBOSE:SAFESEH|安全な例外の処理と互換性がないモジュールに関する情報が表示されます[/SAFESEH](safeseh-image-has-safe-exception-handlers.md)が指定されていません。|
|/VERBOSE:UNUSEDLIBS|イメージの作成時に使用されていないライブラリ ファイルに関する情報を表示します。|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 展開、**リンカー**フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. 追加するには、オプション、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
