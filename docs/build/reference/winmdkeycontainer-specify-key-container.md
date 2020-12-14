---
description: 詳細情報:/WINMDKEYCONTAINER (キーコンテナーの指定)
title: /WINMDKEYCONTAINER (キー コンテナーの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 94b203c56b7724c2b2569ba22039da38c4501985
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258994"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (キー コンテナーの指定)

Windows メタデータ (winmd) ファイルに署名するためのキーコンテナーを指定します。

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>解説

は、(winmd) ファイルに適用される [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md) リンカーオプションに似ています。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **Windows メタデータ** ] プロパティページを選択します。

1. [ **Windows メタデータキーコンテナー** ] ボックスに、場所を入力します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
