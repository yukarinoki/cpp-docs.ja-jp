---
description: 詳細については、次を参照してください:/TLBID (TypeLib のリソース ID を指定)
title: /TLBID (タイプ ライブラリのリソース ID の指定)
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: 4958229cbebe988867c5419d7953b6ffd968e45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230017"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (タイプ ライブラリのリソース ID の指定)

```
/TLBID:id
```

## <a name="arguments"></a>引数

*id*<br/>
リンカーによって作成されたタイプライブラリのユーザー指定の値。 既定のリソース ID 1 をオーバーライドします。

## <a name="remarks"></a>解説

属性を使用するプログラムをコンパイルすると、リンカーによってタイプライブラリが作成されます。 リンカーによって、タイプライブラリにリソース ID 1 が割り当てられます。

このリソース ID が既存のリソースのいずれかと競合する場合は、/TLBID. で別の ID を指定できます。 に渡すことができる値の範囲 `id` は、1 ~ 65535 です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **埋め込み IDL** ] プロパティページをクリックします。

1. **TypeLib リソース ID** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
