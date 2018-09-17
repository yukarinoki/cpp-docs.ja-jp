---
title: -DELAYSIGN (アセンブリの部分署名) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs:
- C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f1551789c800e298396d932a4cc8c4f65aa6c79
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699804"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (アセンブリの部分署名)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>引数

**違います**<br/>
アセンブリが部分的に署名されていないことを指定します。

## <a name="remarks"></a>Remarks

使用 **/DELAYSIGN**公開キーをアセンブリに配置する場合。 既定値は **/delaysign:no です**します。

**/DELAYSIGN**オプションも何も起こりません併用しない限り、 [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)または[/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)します。

アセンブリに完全に署名するように指定すると、コンパイラはマニフェスト (アセンブリ メタデータ) を含むファイルをハッシュし、秘密キーでそのハッシュに署名します。 結果として得られるデジタル署名は、マニフェストを含むファイルに格納されます。 アセンブリが遅延署名されたときに、リンカーはいないコンピューティングし、署名を後で追加できるように、署名が予約領域をファイルに保存します。

たとえばを使用して **/DELAYSIGN**と、テスト時に、アセンブリをグローバル キャッシュに格納できます。 テスト後に、アセンブリに秘密キーを配置することで、アセンブリを完全署名できます。

参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C +/cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)と[Delay Signing an Assembly](/dotnet/framework/app-domains/delay-sign-assembly)アセンブリへの署名の詳細についてはします。

アセンブリの生成に影響するその他のリンカー オプションがあります。

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. オプションを入力、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)