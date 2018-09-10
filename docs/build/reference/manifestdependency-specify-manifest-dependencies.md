---
title: -MANIFESTDEPENDENCY (マニフェストの依存関係の指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82bd32bec0e665f815563ccea2ee05f6ae5172
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315419"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Remarks

/MANIFESTDEPENDENCY を使用してでは、属性を指定できます、\<依存関係 > マニフェスト ファイルのセクション。

参照してください[/MANIFEST (アセンブリ マニフェストを作成して並列)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)についてはマニフェスト ファイルを作成する方法。

詳細については、\<依存関係 > セクションのマニフェスト ファイルを参照してください。[発行者構成ファイル](/windows/desktop/SbsCs/publisher-configuration-files)します。

/MANIFESTDEPENDENCY 情報は、2 つの方法のいずれかでリンカーに渡すことができます。

- コマンドラインで直接 (または応答ファイル内)/MANIFESTDEPENDENCY を使用します。

- 使用して、[コメント](../../preprocessor/comment-c-cpp.md)プラグマ。

次の例では、プラグマを使用して渡す/MANIFESTDEPENDENCY コメント

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

その結果、マニフェスト ファイルで次のエントリには。

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

同じ/MANIFESTDEPENDENCY コメントは、コマンドラインで渡されることができます。

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

リンカーは/MANIFESTDEPENDENCY コメントの収集、重複するエントリを削除し、マニフェスト ファイルに結果の XML 文字列を追加します。  リンカーは、競合するエントリを検出します。、マニフェスト ファイルは破損し、アプリケーションは起動に失敗場合、(エントリは、エラーの原因を示す、イベント ログに追加される可能性があります)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **マニフェスト ファイル**プロパティ ページ。

1. 変更、**追加のマニフェストの依存関係**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)