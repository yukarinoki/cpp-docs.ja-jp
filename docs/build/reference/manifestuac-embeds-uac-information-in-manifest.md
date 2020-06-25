---
title: /MANIFESTUAC (UAC 情報をマニフェストに組み込む)
ms.date: 06/12/2020
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
ms.openlocfilehash: 96719c6f6f5359afb03b967524b1f65db6dc664a
ms.sourcegitcommit: 8645408c7929558b8162f781776d0908d790a41c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85334930"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (UAC 情報をマニフェストに組み込む)

ユーザー アカウント制御 (UAC) 情報をプログラム マニフェストに組み込むかどうかを指定します。

## <a name="syntax"></a>構文

> **`/MANIFESTUAC`**\
> **`/MANIFESTUAC:NO`**\
> **`/MANIFESTUAC:`**_`level`_\
> **`/MANIFESTUAC:`**_`uiAccess`_\
> **`/MANIFESTUAC:`**_`fragment`_

### <a name="parameters"></a>パラメーター

**`NO`**<br/>
リンカーでは、UAC 情報がプログラムマニフェストに埋め込まれません。

*`level`*<br/>
**`level=`** の後に **`'asInvoker'`** 、、またはのいずれかが続き **`'highestAvailable'`** **`'requireAdministrator'`** ます。 既定値は **`'asInvoker'`** です。 詳細については、「[解説](#remarks)」を参照してください。

*`uiAccess`*<br/>
**`uiAccess='true'`** アプリケーションでユーザーインターフェイスの保護レベルをバイパスし、デスクトップ上のアクセス許可の高いウィンドウへの入力をドライブする場合は、それ以外の場合は **`uiAccess='false'`** 。 既定値は **`uiAccess='false'`** です。 **`uiAccess='true'`** ユーザーインターフェイスのユーザー補助アプリケーションの場合にのみ、この引数をに設定します。

*`fragment`*<br/>
およびの値を格納している文字列 *`level`* *`uiAccess`* 。 必要に応じて、二重引用符で囲むこともできます。 詳細については、「[解説](#remarks)」を参照してください。

## <a name="remarks"></a>注釈

コマンドラインで複数のオプションを指定すると **`/MANIFESTUAC`** 、最後に入力したものが優先されます。

の選択肢は次のとおりです **`/MANIFESTUAC:`** _`level`_ 。

- **`level='asInvoker'`**: アプリケーションは、それを開始したプロセスと同じアクセス許可レベルで実行されます。 [**管理者として実行**] を選択すると、アプリケーションをより高いアクセス許可レベルに昇格させることができます。

- **`level='highestAvailable'`**: アプリケーションは、可能な限り高いアクセス許可レベルで実行されます。 アプリケーションを起動するユーザーが Administrators グループのメンバーである場合、このオプションはと同じ **`level='requireAdministrator'`** です。 利用可能な最も高いアクセス許可レベルが、開始プロセスのレベルよりも高い場合は、資格情報の入力が求められます。

- **`level='requireAdministrator'`**: アプリケーションは管理者権限を使用して実行されます。 アプリケーションを開始するユーザーは、管理者グループのメンバーである必要があります。 開いているプロセスが管理者権限で実行されていない場合は、資格情報の入力が求められます。

*`level`* オプションを使用して、値と値の両方を *`uiAccess`* 1 つの手順で指定でき **`/MANIFESTUAC:`** _`fragment`_ ます。 fragment は、次の形式で指定します。

> **`/MANIFESTUAC:`** \[ **`"`** ] **`level=`** { **`'asInvoker'`** | **`'highestAvailable'`** | **`'requireAdministrator'`** } **`uiAccess=`** { **`'true'`** | **`'false'`** } \[ **`"`** ]

次に例を示します。

**`/MANIFESTUAC:"level='highestAvailable' uiAccess='true'"`**

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **マニフェストファイル**] プロパティページを選択します。

1. **ユーザーアカウント制御 (uac)**、 **uac 実行レベル**、および**uac バイパスの UI 保護**プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>、<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>、および <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A> を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
