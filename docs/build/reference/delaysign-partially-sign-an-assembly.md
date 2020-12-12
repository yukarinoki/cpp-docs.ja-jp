---
description: 詳細情報:/DELAYSIGN (アセンブリの部分署名)
title: /DELAYSIGN (アセンブリの部分署名)
ms.date: 11/04/2016
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
ms.openlocfilehash: 40eeaef958b6a188fd4739fcdc0f5ef5123b220a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201483"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (アセンブリの部分署名)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>引数

**NO**<br/>
アセンブリを部分署名しないことを指定します。

## <a name="remarks"></a>解説

公開キーをアセンブリに配置するだけの場合は、 **/DELAYSIGN** を使用します。 既定値は **/DELAYSIGN: NO** です。

**/DELAYSIGN** オプションは、 [/Keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)または [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)と共に使用しない限り、効果はありません。

アセンブリに完全に署名するように指定すると、コンパイラはマニフェスト (アセンブリ メタデータ) を含むファイルをハッシュし、秘密キーでそのハッシュに署名します。 結果として得られるデジタル署名は、マニフェストを含むファイルに格納されます。 アセンブリが遅延署名されている場合、リンカーは署名を計算して保存しませんが、後で署名を追加できるようにファイルに領域を確保します。

たとえば、 **/DELAYSIGN** を使用すると、テスト担当者はアセンブリをグローバルキャッシュに配置できます。 テスト後に、アセンブリに秘密キーを配置することで、アセンブリに完全署名できます。

アセンブリに署名する方法の詳細については、「 [厳密な名前のアセンブリ (アセンブリ署名) (C++/cli](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) )」および「アセンブリへの [遅延署名](/dotnet/framework/app-domains/delay-sign-assembly) 」を参照してください。

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
