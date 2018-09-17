---
title: -MANIFESTUAC (UAC 情報をマニフェスト) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs:
- C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b3997f8beb414992464c51ca1c1fd944145c43d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715144"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (UAC 情報をマニフェストに組み込む)

ユーザー アカウント制御 (UAC) 情報をプログラム マニフェストに組み込むかどうかを指定します。

## <a name="syntax"></a>構文

```
/MANIFESTUAC
/MANIFESTUAC:NO
/MANIFESTUAC:fragment
/MANIFESTUAC:level=_level
/MANIFESTUAC:uiAccess=_uiAccess
```

### <a name="parameters"></a>パラメーター

*フラグメント*<br/>
`level` 値および `uiAccess` 値を格納する文字列。 詳細については、このトピックで後述する「解説」を参照してください。

*レベル (_l)*<br/>
いずれかの*asInvoker*、 *highestAvailable*、または*requireAdministrator*します。 既定値は asInvoker です。 詳細については、このトピックで後述する「解説」を参照してください。

*_uiAccess*<br/>
アプリケーションがユーザー インターフェイスの保護レベルをバイパスし、入力をデスクトップ上のアクセス許可の高いウィンドウにアクセスできるようにするには `true`、それ以外の場合は `false`。 既定値は `false` です。 `true` の設定は、ユーザー インターフェイスのユーザー補助アプリケーションでのみ行います。

## <a name="remarks"></a>Remarks

コマンド ラインで複数の /MANIFESTUAC オプションを指定した場合は、最後に入力したオプションが優先されます。

/MANIFESTUAC:level に指定できるのは、次のとおりです。

- `asInvoker`: アプリケーションは、アプリケーションを開始したプロセスと同じアクセス許可で実行されます。 アプリケーションを選択してより高いアクセス許可レベルに昇格させることができます**管理者として実行**します。

- highestAvailable: アプリケーションは、可能な限り高いアクセス許可レベルで実行されます。 アプリケーションを開始するユーザーが管理者グループのメンバーである場合、このオプションは requireAdministrator と同じです。 使用可能な最も高いアクセス許可レベルが、開始したプロセスのレベルより高い場合は、資格情報の入力が求められます。

- requireAdministrator: アプリケーションは管理者のアクセス許可で実行されます。 アプリケーションを開始するユーザーは、管理者グループのメンバーである必要があります。 開始したプロセスが管理者のアクセス許可で実行されない場合は、資格情報の入力が求められます。

/MANIFESTUAC:fragment オプションを使用することにより、level 値と uiAccess 値の指定を 1 ステップで行うことができます。 fragment は、次の形式で指定します。

```
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**マニフェスト ファイル**プロパティ ページ。

1. 変更、**を有効にするユーザー アカウント制御 (UAC)**、 **UAC の実行レベル**、および**UAC による UI 保護のバイパス**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>、<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>、および <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A> を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)