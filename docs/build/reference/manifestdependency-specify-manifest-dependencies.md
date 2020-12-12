---
description: 詳細情報:/manifestdependency (マニフェストの依存関係の指定)
title: /MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
ms.openlocfilehash: 129dc84818b0bda9b2106c0d07dca5b605dc6f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199168"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>解説

/Manifestdependency を使用すると、マニフェストファイルのセクションに配置される属性を指定でき \<dependency> ます。

マニフェストファイルの作成方法については、「 [マニフェスト (Side-by-side アセンブリマニフェストを作成する)](manifest-create-side-by-side-assembly-manifest.md) 」を参照してください。

\<dependency>マニフェストファイルのセクションの詳細については、「[発行者構成ファイル](/windows/win32/SbsCs/publisher-configuration-files)」を参照してください。

/Manifestdependency 情報は、次の2つの方法のいずれかでリンカーに渡すことができます。

- コマンドライン (または応答ファイル内) で、/manifestdependencyを直接使用します。

- [Comment](../../preprocessor/comment-c-cpp.md)プラグマを使用します。

次の例では、プラグマで渡された/manifestdependency コメントを示しています。

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

この結果、マニフェストファイルに次のエントリが生成されます。

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

次のように、同じ/manifestdependency コメントをコマンドラインで渡すことができます。

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

リンカーによって、依存関係のコメントが収集され、重複するエントリが削除されてから、結果として生成された XML 文字列がマニフェストファイルに追加されます。  リンカーが競合するエントリを検出すると、マニフェストファイルが破損し、アプリケーションを起動できなくなります (エラーの原因を示すエントリがイベントログに追加される場合があります)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **マニフェストファイル**] プロパティページを選択します。

1. " **追加のマニフェストの依存関係** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
