---
title: /FILEALIGN (ファイル内の配置セクション) |Microsoft ドキュメント
ms.date: 10/23/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /filealign
dev_langs:
- C++
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a737801663a2c7c1e896166291a1635fbbe6c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373271"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN (ファイル内の配置セクション)

**/FILEALIGN**リンカー オプションを使用して、指定したサイズの倍数として、出力ファイルに書き込まれるセクションのアラインメントを指定できます。

## <a name="syntax"></a>構文

> __/FILEALIGN:__*サイズ*

### <a name="parameters"></a>パラメーター

*size*  
セクション配置サイズ バイト数は、2 の累乗にする必要があります。

## <a name="remarks"></a>コメント

**/FILEALIGN**オプションの倍数である境界で出力ファイル内の各セクションに合わせて、リンカーの設定により、*サイズ*値。 既定では、リンカーは、固定の配置のサイズを使用しません。

**/FILEALIGN**オプションは、ディスク使用率をより効率的に使用できますか、ページをディスクから読み込まれます高速化します。 セクション サイズが小さくは、ダウンロードを小さく保ちの小さなデバイスで実行されるアプリに役立つ可能性があります。 ディスク上のセクションの配置では、メモリ内の配置は影響しません。

出力ファイル内のセクションに関する情報を表示するには、[DUMPBIN](dumpbin-reference.md) を使用します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**コマンドライン**プロパティ ページで、**リンカー**フォルダーです。

1. オプション名を入力 **/FILEALIGN:** およびのサイズ、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
[リンカー オプション](../../build/reference/linker-options.md)