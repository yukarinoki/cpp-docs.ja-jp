---
title: /DRIVER (Windows NT カーネル モード ドライバー)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: c935c20d6c1c009cff64d48e0c0122c8b91bbba3
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041160"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT カーネル モード ドライバー)

>/DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>注釈

Windows NT カーネルモードドライバーをビルドするには、 **/DRIVER** リンカーオプションを使用します。

**/DRIVER: UPONLY** は、プロセッサ (up) ドライバーであることを指定するために、出力ヘッダーの特性に **IMAGE_FILE_UP_SYSTEM_ONLY** ビットを追加します。 オペレーティングシステムは、マルチプロセッサ (MP) システムでのアップドライバの読み込みを拒否します。

**/DRIVER: WDM** により、リンカーはオプションのヘッダーの dllcharacteristics フィールドに **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** ビットを設定します。

**/DRIVER**が指定されていない場合、これらのビットはリンカーによって設定されません。

**/DRIVER**が指定されている場合:

- **/Fixed: NO** が有効です。 詳細については、「 [/fixed (固定ベースアドレス)](fixed-fixed-base-address.md)」を参照してください。

- 出力ファイルの拡張子は、.sys に設定されます。 **/Out**を使用して、既定のファイル名と拡張子を変更します。 詳細については、「 [/out (出力ファイル名)](out-output-file-name.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **システム** ] プロパティページをクリックします。

1. **ドライバー**のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「 [VCLinkerTool プロパティ](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver)」を参照してください。

## <a name="see-also"></a>参照

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
