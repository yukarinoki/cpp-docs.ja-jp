---
title: -TLBID (タイプ ライブラリのリソース ID を指定) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e34e4d27c374fddd7710431e3a09f6a9ccfc802d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701315"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (タイプ ライブラリのリソース ID の指定)

```
/TLBID:id
```

## <a name="arguments"></a>引数

*ID*<br/>
リンカーによって作成されたタイプ ライブラリのユーザー指定の値。 1 の既定のリソース ID をオーバーライドします。

## <a name="remarks"></a>Remarks

属性を使用するプログラムをコンパイルするときに、リンカーは、タイプ ライブラリを作成します。 リンカーでは、タイプ ライブラリを 1 のリソース ID を割り当てます。

このリソース ID は、いずれか、既存のリソースと競合している場合は、/TLBID で別の ID を指定できます。 渡すことができる値の範囲`id`は 1 ~ 65535 です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**埋め込み IDL**プロパティ ページ。

1. 変更、 **TypeLib リソース ID**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)