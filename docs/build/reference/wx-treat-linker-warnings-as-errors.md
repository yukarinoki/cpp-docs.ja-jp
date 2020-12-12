---
description: 詳細情報:/WX (リンカー警告をエラーとして扱う)
title: /WX (リンカー警告をエラーとして扱う)
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: 965c48ff9c9f975350f3c1e54d8090823be8fd2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261035"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (リンカー警告をエラーとして扱う)

```
/WX[:NO]
```

## <a name="remarks"></a>解説

/WX を指定すると、リンカーが警告を生成した場合に出力ファイルが生成されません。

これは、コンパイラの **/wx** に似ています ( [/w、/W0、/W1、/W2、/W3、/W4、/W1、/W2、/W3、/W4、/Wall、/wd、/we、/wo、/Wv、/Wx (警告レベル)](compiler-option-warning-level.md) など)。 ただし、コンパイルに **/wx** を指定しても、 **/wx** がリンクフェーズに対して有効であることを意味するわけではありません。各ツールに対して、 **/wx** を明示的に指定する必要があります。

既定では、 **/wx** は無効です。 リンカー警告をエラーとして扱うには、 **/wx** を指定します。 **/Wx: NO** は **/wx** を指定しないと同じです。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
