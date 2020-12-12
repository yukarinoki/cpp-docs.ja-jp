---
description: 詳細については、次を参照してください:/DELAYLOAD (遅延読み込みのインポート)
title: /DELAYLOAD (遅延読み込みのインポート)
ms.date: 11/04/2016
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
ms.openlocfilehash: 9f6a91a102b66a16896d51b960d44273a7935d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201496"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (遅延読み込みのインポート)

> **/DELAYLOAD:**_dllname_

## <a name="parameters"></a>パラメーター

*dllname*<br/>
遅延読み込みする DLL の名前。

## <a name="remarks"></a>解説

/DELAYLOAD オプションを指定すると、`dllname` で指定された DLL は、その DLL 内の関数に対するプログラムの最初の呼び出しが行われたときのみ読み込まれます。 詳細については、「 [Delay-Loaded dll のリンカーサポート](linker-support-for-delay-loaded-dlls.md)」を参照してください。 このオプションは、選択した DLL を指定するのに必要なだけ繰り返して使用できます。 プログラムを Delayimp.lib にリンクする場合は、Delayimp.lib を使用する必要があります。または、独自の遅延読み込みヘルパー関数を実装することもできます。

[/DELAY](delay-delay-load-import-settings.md)オプションは、遅延読み込みされた各 DLL のバインドオプションと読み込みオプションを指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーで、[ **入力** ] プロパティページを選択します。

1. " **Dll の遅延読み込み** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
