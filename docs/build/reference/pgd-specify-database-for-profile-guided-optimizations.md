---
description: 詳細については、次を参照してください:/PGD (Profile-Guided の最適化のためにデータベースを指定)
title: /PGD (ガイド付き最適化のプロファイル用のデータベースの指定)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 7030ddaef33c6ee794c470df2c42c72d78555369
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225987"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (ガイド付き最適化のプロファイル用のデータベースの指定)

**/PGD オプションは非推奨とされます。** Visual Studio 2015 以降では、代わりに、 [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) リンカーオプションを使うことをお勧めします。 このオプションは、ガイド付き最適化のプロファイルプロセスで使用される .pgd ファイルの名前を指定するために使用されます。

## <a name="syntax"></a>構文

> **/PGD:**_ファイル名_

## <a name="argument"></a>引数

*filename*<br/>
実行中のプログラムに関する情報を保持するために使用される .pgd ファイルの名前を指定します。

## <a name="remarks"></a>解説

非推奨の [/ltcg: PGINSTRUMENT](ltcg-link-time-code-generation.md) オプションを使用する場合は、 **/PGD** を使用して、.pgd ファイルの既定以外の名前または場所を指定します。 **/PGD** を指定しない場合、.pgd ファイルの基本名は出力ファイル (.exe または .dll) のベース名と同じになり、リンクが呼び出されたディレクトリに作成されます。

非推奨の **/ltcg: PGOPTIMIZE** オプションを使用する場合は、 **/PGD** オプションを使用して、最適化されたイメージの作成に使用する .pgd ファイルの名前を指定します。 *Filename* 引数は、 **/LTCG: pginstrument** に指定された *ファイル名* と一致している必要があります。

詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー** の  >  **最適化**] プロパティページを選択します。

1. **ガイド付きデータベースのプロファイル** プロパティを変更します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
