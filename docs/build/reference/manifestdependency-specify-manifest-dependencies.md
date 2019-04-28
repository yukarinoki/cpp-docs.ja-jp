---
title: /MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
ms.openlocfilehash: 676059b8d398fd108d8f8fc163c85a3da3c657b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321593"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Remarks

/MANIFESTDEPENDENCY を使用してでは、属性を指定できます、\<依存関係 > マニフェスト ファイルのセクション。

参照してください[/MANIFEST (アセンブリ マニフェストを作成して並列)](manifest-create-side-by-side-assembly-manifest.md)についてはマニフェスト ファイルを作成する方法。

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

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **リンカー** > **マニフェスト ファイル**プロパティ ページ。

1. 変更、**追加のマニフェストの依存関係**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
