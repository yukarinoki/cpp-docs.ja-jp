---
title: /RELEASE (チェックサムの設定)
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: 9192768f711da721cfef65314573d78caa8c2442
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426642"
---
# <a name="release-set-the-checksum"></a>/RELEASE (チェックサムの設定)

```
/RELEASE
```

## <a name="remarks"></a>Remarks

/RELEASE オプションは、.exe ファイルのヘッダーにチェックサムを設定します。

オペレーティング システムでは、デバイス ドライバーのチェックサムが必要です。 将来のオペレーティング システムとの互換性を確保する、デバイス ドライバーのリリース バージョンのチェックサムを設定します。

/RELEASE オプションは既定で設定時に、[中に/subsystem:native が](../../build/reference/subsystem-specify-subsystem.md)オプションを指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**詳細**プロパティ ページ。

1. 変更、**チェックサムの設定**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
