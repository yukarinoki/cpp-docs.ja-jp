---
description: 詳細情報:/WINMDKEYFILE (winmd キーファイルの指定)
title: /WINMDKEYFILE (キー ファイルの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 0e7b23de62613f51c3824b107e55180bb54780d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258903"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (キー ファイルの指定)

Windows ランタイムメタデータ (winmd) ファイルに署名するキーまたはキーペアを指定します。

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>解説

は、winmd ファイルに適用される [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) リンカーオプションに似ています。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **Windows メタデータ** ] プロパティページを選択します。

1. [ **Windows メタデータキーファイル** ] ボックスに、ファイルの場所を入力します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
