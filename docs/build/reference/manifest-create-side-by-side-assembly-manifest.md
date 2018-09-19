---
title: -マニフェスト (サイド バイ サイド アセンブリ マニフェストを作成する) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 468c41fe9cda752dd2727e6c9ec5d29781ef113d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710412"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (side-by-side アセンブリ マニフェストを作成する)

```
/MANIFEST[:{EMBED[,ID=#]|NO}]
```

## <a name="remarks"></a>Remarks

/MANIFEST は、リンカーが side-by-side マニフェストファイルを作成することを指定します。 マニフェスト ファイルの詳細については、次を参照してください。 [Manifest Files Reference](/windows/desktop/SbsCs/manifest-files-reference)します。

既定値は、"/MANIFEST" です。

/MANIFEST:EMBED オプションは、リンカーが RT_MANIFEST 型のリソースとしてイメージにマニフェスト ファイルを埋め込む必要があることを指定します。 省略可能な `ID` パラメーターは、マニフェストで使用するリソース ID です。 実行可能ファイルの場合は値 1 を使用します。 DLL の場合は値 2 を使用して、プライベート依存関係を指定できるようにします。 `ID` パラメーターを指定しない場合、/DLL オプションが設定されている場合の既定値は 2、それ以外の場合の既定値は 1 になります。

Visual Studio 2008 以降では、実行可能ファイルのマニフェストのファイルには、ユーザー アカウント制御 (UAC) 情報を指定するセクションが含まれます。 /MANIFEST を指定するが、いずれも指定する場合[/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)も[/DLL](../../build/reference/dll-build-a-dll.md)、UAC レベルのセットが既定の UAC フラグメント*asInvoker*マニフェストに挿入されます。 UAC レベルの詳細については、次を参照してください。 [/MANIFESTUAC (UAC 情報をマニフェスト)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)します。

UAC の既定の動作を変更するには、次のいずれかを行います。

- /MANIFESTUAC オプションを指定して、UAC レベルを所定の値に設定します。

- マニフェストに UAC フラグメントを生成しない場合は、/MANIFESTUAC:NO オプションを指定します。

/MANIFEST を指定しないが、指定したかどうか[/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)コメント、マニフェスト ファイルが作成されます。 /MANIFEST:NO を指定すると、マニフェスト ファイルは作成されません。

/MANIFEST を指定すると、マニフェスト ファイルの名前は出力ファイルの名前と同じになりますが、ファイル名に .manifest が追加されます。 たとえば、出力ファイルの名前が MyFile.exe の場合、マニフェスト ファイル名は MyFile.exe.manifest になります。  /Manifestfile:*名前*、マニフェストの名前がで指定した*名前*します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**マニフェスト ファイル**プロパティ ページ。

1. 変更、**マニフェストの生成**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)