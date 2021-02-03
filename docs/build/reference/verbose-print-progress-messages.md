---
description: 詳細情報:/VERBOSE (進行状況メッセージの出力)
title: /VERBOSE (進行状況メッセージの出力)
ms.date: 02/03/2021
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
ms.openlocfilehash: d58a6cc8d75021c78f8161cf12957a77bb26483c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522925"
---
# <a name="verbose-print-progress-messages"></a>`/VERBOSE` (進行状況メッセージの出力)

リンクプロセス中に進行状況メッセージを出力します。

## <a name="syntax"></a>構文

> **`/VERBOSE`**\[**`:`**{**`CLR`**|**`ICF`**|**`INCR`**|**`LIB`**|**`REF`**|**`SAFESEH`**|**`UNUSEDDELAYLOAD`**|**`UNUSEDLIBS`**}\]

## <a name="remarks"></a>解説

リンカーは、リンクセッションの進行状況に関する情報を **出力** ウィンドウに送信します。 コマンドラインでは、情報は標準出力に送信され、ファイルにリダイレクトできます。

| オプション | [説明] |
| ------------ | ----------------- |
| **`/VERBOSE`** | リンク プロセスに関する詳細情報を表示します。 |
| **`/VERBOSE:CLR`** | を使用してコンパイルされたオブジェクトおよびメタデータに固有のリンカーアクティビティについての情報を表示 [`/clr`](clr-common-language-runtime-compilation.md) します。 |
| **`/VERBOSE:ICF`** | を使用した結果として得られるリンカーアクティビティに関する情報を表示 [`/OPT:ICF`](opt-optimizations.md) します。 |
| **`/VERBOSE:INCR`** | インクリメンタル リンク プロセスに関する情報を表示します。 |
| **`/VERBOSE:LIB`** | 検索されたライブラリだけを示す進行状況メッセージを表示します。<br/> 表示される情報には、ライブラリ検索プロセスが含まれます。 各ライブラリとオブジェクト名 (完全パス)、ライブラリから解決されるシンボル、およびシンボルを参照するオブジェクトの一覧が表示されます。 |
| **`/VERBOSE:REF`** | を使用した結果として得られるリンカーアクティビティに関する情報を表示 [`/OPT:REF`](opt-optimizations.md) します。 |
| **`/VERBOSE:SAFESEH`** | 指定されていない場合に、安全な構造化例外処理と互換性のないモジュールに関する情報を表示 [`/SAFESEH`](safeseh-image-has-safe-exception-handlers.md) します。 |
| **`/VERBOSE:UNUSEDDELAYLOAD`** | イメージの作成時にシンボルが使用されていない、遅延読み込みされた Dll に関する情報を表示します。 |
| **`/VERBOSE:UNUSEDLIBS`** | イメージの作成時に使用されていないライブラリ ファイルに関する情報を表示します。 |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [ **追加オプション** ] ボックスにオプションを追加します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
