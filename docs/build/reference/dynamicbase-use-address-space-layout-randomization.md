---
title: -DYNAMICBASE (使用してアドレス空間レイアウトのランダム化) |Microsoft Docs
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 896e2eca86b7694c8b3b951a8eb080a4cf9e7684
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223457"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (ASLR (Address Space Layout Randomization) の使用)

ランダムに再ベースできる読み込み時に Windows Vista で初めて提供された Windows のアドレス空間レイアウト randomization (ASLR) 機能を使用して実行可能イメージを生成するかどうかを指定します。

## <a name="syntax"></a>構文

> **/DYNAMICBASE****[: NO]**

## <a name="remarks"></a>Remarks

**/DYNAMICBASE**オプションのヘッダーを変更する、*実行可能イメージ*、.dll または .exe ファイルをアプリケーションが、読み込み時にランダムにリベースする必要があり、仮想アドレスが有効かどうかを示すためにヒープの仮想メモリの場所に影響を与える割り当てのランダム化スタック、およびその他のオペレーティング システムの割り当て。 **/DYNAMICBASE**オプションは、32 ビットと 64 ビットの両方のイメージに適用されます。 ASLR は、Windows Vista およびそれ以降のオペレーティング システムでサポートされます。 オプションは、以前のオペレーティング システムによって無視されます。

既定では、 **/DYNAMICBASE**を有効にします。 このオプションを無効にするには、 **/DYNAMICBASE:NO**します。 **/DYNAMICBASE**オプションが必要です、 [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)オプションに影響を与えます。

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **詳細**プロパティ ページ。

1. 変更、**ランダム化されたベース アドレス**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Windows ISV Software Security Defenses](https://msdn.microsoft.com/library/bb430720.aspx)