---
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
ms.openlocfilehash: aa8cc5a565b4af625a1ee85f67ca1c82e065486b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416281"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (遅延読み込みのインポート)

> **/DELAYLOAD:**_dllname_

## <a name="parameters"></a>パラメーター

*dllname*<br/>
遅延読み込みする DLL の名前。

## <a name="remarks"></a>Remarks

/DELAYLOAD オプションを指定すると、`dllname` で指定された DLL は、その DLL 内の関数に対するプログラムの最初の呼び出しが行われたときのみ読み込まれます。 詳細については、次を参照してください。[リンカーによる dll の Delay-Loaded](../../build/reference/linker-support-for-delay-loaded-dlls.md)します。 このオプションは、選択した DLL を指定するのに必要なだけ繰り返して使用できます。 プログラムを Delayimp.lib にリンクする場合は、Delayimp.lib を使用する必要があります。または、独自の遅延読み込みヘルパー関数を実装することもできます。

[/Delay](../../build/reference/delay-delay-load-import-settings.md)オプションは、バインドと読み込みの遅延読み込み dll はごとのオプションを指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **リンカー**フォルダーを選択、**入力**プロパティ ページ。

1. 変更、 **Dll の遅延読み込み**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
