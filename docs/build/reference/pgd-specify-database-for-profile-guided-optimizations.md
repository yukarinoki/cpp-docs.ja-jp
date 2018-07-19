---
title: /PGD (プロファイル ガイド付き最適化のデータベースの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7685f99137a1b599a5f9020fac9e3cae4ba3bc3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378445"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (ガイド付き最適化のプロファイル用のデータベースの指定)

**/PGD オプションは推奨されません。** 必要に応じて、Visual Studio 2015 以降、 [/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)リンカー オプションの代わりにします。 このオプションを使用して、プロファイル ガイド付き最適化のプロセスによって使用される .pgd ファイルの名前を指定します。

## <a name="syntax"></a>構文

> **/PGD:**_ファイル名_

## <a name="argument"></a>引数

*ファイル名*<br/>
実行中のプログラムに関する情報を保持するために使用される .pgd ファイルの名前を指定します。

## <a name="remarks"></a>コメント

非推奨を使用する場合[/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)オプションを使用して **/PGD**既定以外の名前または .pgd ファイルの場所を指定します。 指定しない場合 **/PGD**、.pgd ファイルのベース名は、出力ファイル (.exe または .dll) のベース名と同じとは、リンクの呼び出し元となる同じディレクトリに作成します。

非推奨の使用時に **/LTCG:PGOPTIMIZE**オプションを使用して、 **/PGD**オプションを使用して、最適化されたイメージを作成する .pgd ファイルの名前を指定します。 *Filename*引数に一致する必要があります、 *filename*に指定された **/LTCG:PGINSTRUMENT**です。

詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **最適化**プロパティ ページ。

1. 変更、**プロファイル ガイド付きデータベース**プロパティです。 選択**OK**して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
