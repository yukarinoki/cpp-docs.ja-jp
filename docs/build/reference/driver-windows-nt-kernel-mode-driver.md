---
title: -DRIVER (Windows NT カーネル モード ドライバー) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae096c502cdc94d47a516caf4c29ac4f3eceb4b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705550"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT カーネル モード ドライバー)

>/DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Remarks

使用して、 **/DRIVER**リンカー オプションを Windows NT カーネル モード ドライバーをビルドします。

**/DRIVER:UPONLY**リンカーに追加、 **IMAGE_FILE_UP_SYSTEM_ONLY**ビット、ユニプロセッサ (UP) ドライバーを指定するための出力ヘッダーの特性をします。 オペレーティング システムは、マルチプロセッサ (MP) システムで、UP ドライバーの読み込みが拒否されます。

**/DRIVER:WDM**リンカーを設定する、 **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER**省略可能なヘッダーの DllCharacteristics フィールド内のビットします。

場合 **/DRIVER**が指定されていない、リンカーによってこれらのビットが設定されていません。

場合 **/DRIVER**を指定します。

- **/FIXED:NO**が有効になっています。 詳細については、「[/FIXED (固定ベース アドレス)](../../build/reference/fixed-fixed-base-address.md)」を参照してください。

- 出力ファイルの拡張機能は、.sys に設定されます。 使用 **/out**既定のファイル名と拡張子を変更します。 詳細については、「[/OUT (出力ファイル名)](../../build/reference/out-output-file-name.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**システム**プロパティ ページ。

1. 変更、**ドライバー**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 参照してください[VCLinkerTool.driver プロパティ](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver)します。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
