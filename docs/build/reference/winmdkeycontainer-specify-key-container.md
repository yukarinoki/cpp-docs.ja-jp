---
title: /WINMDKEYCONTAINER (キー コンテナーの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 8d26c49a8cf4a1f71841fabdd4ec30fb437ad349
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532237"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (キー コンテナーの指定)

Windows メタデータ (.winmd) ファイルに署名するキー コンテナーを指定します。

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Remarks

似ています、 [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)リンカー オプション (.winmd) ファイルに適用されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、 **Windows メタデータ**プロパティ ページ。

1. **Windows メタデータ キー コンテナー**ボックスに、場所を入力します。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)