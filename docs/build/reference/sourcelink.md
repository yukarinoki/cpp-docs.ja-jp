---
title: /SOURCELINK (PDB に Sourcelink ファイルを含める)
description: マイクロソフト C++ の /SOURCELINK リンカー オプションのリファレンス ガイド。
ms.date: 03/31/2020
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: bde55c401e17f7b3c84ffcdad29dda2badcc260b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336065"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/ソースリンク (PDB にソース リンク ファイルを含める)

リンカーによって生成される PDB ファイルに含めるソース リンク構成ファイルを指定します。

## <a name="syntax"></a>構文

> **`/SOURCELINK:`**_`filename`_

## <a name="arguments"></a>引数

*Filename*<br/>
デバッガーで表示するソース ファイルの URL へのローカル ファイル パスの単純なマッピングを含む、JSON 形式の構成ファイルを指定します。 このファイルの形式の詳細については、「[ソース リンク JSON スキーマ](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md#source-link-json-schema)」を参照してください。

## <a name="remarks"></a>解説

ソース リンクは、バイナリのソース デバッグを提供するための言語およびソース管理のシステムです。 ソース リンクは、Visual Studio 2017 バージョン 15.8 以降のネイティブ C++ バイナリでサポートされています。 ソースリンクの概要については、[ソースリンク](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md)を参照してください。 プロジェクトでソースリンクを使用する方法と、プロジェクトの一部として SourceLink ファイルを生成する方法については、「[ソースリンクの使用](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects)」を参照してください。

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>ビジュアル スタジオで /ソースリンク リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **[構成プロパティ リン** > **カー** > **コマンド ライン**] プロパティ ページを選択します。

1. [**追加オプション**] ボックスで**`/SOURCELINK:`**_`filename`_**、[OK]** または [**適用**] を選択して変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- このオプションには、プログラム上の同等の機能はありません。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
