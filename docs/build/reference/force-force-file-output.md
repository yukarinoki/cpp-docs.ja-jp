---
title: /FORCE (ターゲットを強制的に出力)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: d1d85174290faa95e73c63a25f7d80c554e83ace
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079624"
---
# <a name="force-force-file-output"></a>/FORCE (ターゲットを強制的に出力)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>解説

/FORCE オプションは、シンボルが参照されているが定義されていないか、または乗算が定義されている場合でも、有効な .exe ファイルまたは DLL を作成するようにリンカーに指示します。

/FORCE オプションは、省略可能な引数を受け取ることができます。

- リンクがシンボルに対して複数の定義を検出したかどうかにかかわらず、/FORCE: MULTIPLE を使用して出力ファイルを作成します。

- /FORCE: 未解決を使用して、リンクが未定義のシンボルを見つけたかどうかにかかわらず、出力ファイルを作成します。 /FORCE: エントリポイントシンボルが未解決の場合、未解決のは無視されます。

引数を指定せずに/FORCE を指定すると、multiple と未解決の両方が示されます。

このオプションを使用して作成されたファイルは、予期したとおりに実行されない可能性があります。 /FORCE オプションが指定されている場合、リンカーは段階的にリンクされません。

モジュールが **/clr**でコンパイルされた場合、 **/force**はイメージを作成しません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. **ソリューションエクスプローラー**でプロジェクトを右クリックし、 **[プロパティ]** を選択します。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加オプション]** ボックスにオプションを入力します。

詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
