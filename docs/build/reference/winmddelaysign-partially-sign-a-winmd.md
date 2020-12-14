---
description: 詳細情報:/WINMDDELAYSIGN (winmd の部分署名)
title: /WINMDDELAYSIGN (winmd の部分署名)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 801b172f52a9beb9d09617644b3096e460359724
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259059"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd の部分署名)

公開キーをファイルに配置することによって、Windows ランタイムメタデータ (winmd) ファイルの部分署名を有効にします。

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>解説

は、winmd ファイルに適用される [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) リンカーオプションに似ています。 公開キーのみを winmd ファイルに格納する場合は、 **/WINMDDELAYSIGN** を使用します。 既定では、リンカーは **/WINMDDELAYSIGN: NO** が指定された場合と同様に動作します。つまり、winmd ファイルに署名しません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **Windows メタデータ** ] プロパティページを選択します。

1. [ **Windows メタデータ遅延署名** ] ボックスの一覧で、必要なオプションを選択します。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
