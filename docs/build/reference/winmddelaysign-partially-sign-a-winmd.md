---
title: /WINMDDELAYSIGN (winmd の部分署名)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 5e6eab3fbc40543b634f03da826d3bd3477b9623
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57421464"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd の部分署名)

ファイルの公開キーを配置することで、Windows ランタイム メタデータ (.winmd) ファイルの部分署名を使用できます。

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Remarks

似ています、 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) .winmd ファイルに適用されるリンカー オプション。 使用**含める**.winmd ファイルに、公開キーのみを配置する場合。 既定では、リンカーの動作として **/winmddelaysign:no です**; 指定された winmd ファイルを署名には、しません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、 **Windows メタデータ**プロパティ ページ。

1. **Windows メタデータ遅延署名**ドロップダウン リスト ボックスで、目的のオプションを選択します。

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
