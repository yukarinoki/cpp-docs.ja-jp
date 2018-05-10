---
title: ドライバー (Windows NT カーネル モード ドライバー) |Microsoft ドキュメント
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
ms.openlocfilehash: 66291391ed38c27ce7446eccc6fca227c7c2c2d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT カーネル モード ドライバー)

>/DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>コメント

使用して、 **/DRIVER**リンカー オプションを Windows NT カーネル モード ドライバーをビルドします。

**/DRIVER:UPONLY**リンカーに追加、 **IMAGE_FILE_UP_SYSTEM_ONLY**ユニプロセッサ (UP) ドライバーであることを指定する出力ヘッダーの特性にビットです。 オペレーティング システムがマルチプロセッサ (MP) システムで UP ドライバーの読み込みを拒否します。

**/DRIVER:WDM**リンカー設定に、 **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER**省略可能なヘッダーの DllCharacteristics フィールド内のビットです。

場合 **/DRIVER**が指定されていない、リンカーによってこれらのビットが設定されていません。

場合 **/DRIVER**を指定します。

- **/FIXED:NO**が有効になっています。 詳細については、「[/FIXED (固定ベース アドレス)](../../build/reference/fixed-fixed-base-address.md)」を参照してください。

- 出力ファイルの拡張子は、.sys に設定されます。 使用して **/out**拡張機能と既定のファイル名を変更します。 詳細については、「[/OUT (出力ファイル名)](../../build/reference/out-output-file-name.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. クリックして、**リンカー**フォルダーです。

1. クリックして、**システム**プロパティ ページ。

1. 変更、**ドライバー**プロパティです。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 参照してください[VCLinkerTool.driver プロパティ](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver)です。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
[リンカー オプション](../../build/reference/linker-options.md)
