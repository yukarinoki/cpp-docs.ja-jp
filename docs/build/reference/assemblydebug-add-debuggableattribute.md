---
description: 詳細については、次を参照してください:/assemblydebug (DebuggableAttribute の追加)
title: /ASSEMBLYDEBUG (DebuggableAttribute の追加)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
ms.openlocfilehash: 7d63ae4ffd86099147b076a499321ed5dcf3ca54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183036"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG (DebuggableAttribute の追加)

```
/ASSEMBLYDEBUG[:DISABLE]
```

/Assemblydebug は、デバッグ情報の追跡を使用して **DebuggableAttribute** 属性を出力し、JIT 最適化を無効にします。 これは、source で次の属性を指定することと同じです。

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

/Assemblydebug: DISABLE は、 **DebuggableAttribute** 属性を出力しますが、デバッグ情報の追跡を無効にし、JIT 最適化を有効にします。 これは、source で次の属性を指定することと同じです。

```
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE
```

既定では、 **DebuggableAttribute** 属性は出力されません。

DebuggableAttribute は、ソースコード内のアセンブリに直接追加することもできます。 たとえば、次のように入力します。

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

## <a name="remarks"></a>解説

マネージイメージをデバッグできるようにするには、明示的に指定する必要があります。 [/Zi](z7-zi-zi-debug-information-format.md)だけでは不十分です。

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **デバッグ** ] プロパティページをクリックします。

1. デバッグ可能 **アセンブリ** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
