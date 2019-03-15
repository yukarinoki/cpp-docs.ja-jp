---
title: /ALLOWBIND (DLL をバインドしない)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
ms.openlocfilehash: bd9976e434441d2480386ee6fa3d0315fd8d2ef5
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "57818844"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL をバインドしない)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Remarks

/ALLOWBIND:NO は DLL のヘッダーにビットを設定して、イメージをバインドできないことを Bind.exe に示します。 DLL がデジタル署名されている場合はバインドしないほうがよいでしょう (バインドによって署名が無効になる)。

/ALLOWBIND 機能の既存の DLL を編集することができます、 [/ALLOWBIND](allowbind.md) EDITBIN ユーティリティのオプション。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 展開**構成プロパティ**、**リンカー**、選び**コマンド ライン**します。

1. 入力`/ALLOWBIND:NO`に**追加オプション**します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[BindImage 関数](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx 関数](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)
