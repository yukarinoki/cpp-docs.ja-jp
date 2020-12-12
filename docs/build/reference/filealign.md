---
description: 詳細情報:/FILEALIGN (ファイル内のセクションの整列)
title: /FILEALIGN (ファイル内のセクションの配置)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: a67cf682c8fe55b80b2253864e08919e08242f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192163"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN (ファイル内のセクションの配置)

**/FILEALIGN** リンカーオプションを使用すると、指定したサイズの倍数として出力ファイルに書き込まれたセクションの配置を指定できます。

## <a name="syntax"></a>構文

> __/FILEALIGN:__*サイズ*

### <a name="parameters"></a>パラメーター

*size*<br/>
セクションの配置サイズ (バイト単位)。2の累乗でなければなりません。

## <a name="remarks"></a>Remarks

**/FILEALIGN** オプションを指定すると、リンカーは、*サイズ* 値の倍数である境界上の出力ファイルの各セクションをアラインします。 既定では、リンカーは固定の配置サイズを使用しません。

**/FILEALIGN** オプションを使用すると、ディスクの使用効率を向上させることができます。また、ディスクからページの読み込みを高速化することもできます。 小さなデバイスで実行されるアプリやダウンロードのサイズを小さくするために、セクションのサイズを小さくすると便利な場合があります。 ディスク上のセクションアラインメントは、メモリ内のアラインメントには影響しません。

出力ファイル内のセクションに関する情報を表示するには、[DUMPBIN](dumpbin-reference.md) を使用します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**リンカー** ] フォルダーの [**コマンドライン**] プロパティページを選択します。

1. オプション名として「 **/FILEALIGN:** 」と入力し、[ **追加オプション** ] ボックスにサイズを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
