---
description: 詳細情報:/RELEASE (チェックサムの設定)
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
ms.openlocfilehash: ed1e55dffb02ace26e91e262bd3e9514f056196e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225324"
---
# <a name="release-set-the-checksum"></a>/RELEASE (チェックサムの設定)

```
/RELEASE
```

## <a name="remarks"></a>解説

/RELEASE オプションは、.exe ファイルのヘッダーにチェックサムを設定します。

オペレーティングシステムには、デバイスドライバーのチェックサムが必要です。 将来のオペレーティングシステムとの互換性を確保するために、デバイスドライバーのリリースバージョンのチェックサムを設定します。

/RELEASE オプションは、 [/SUBSYSTEM: NATIVE](subsystem-specify-subsystem.md) オプションが指定されている場合に既定で設定されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. " **チェックサムの設定** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
