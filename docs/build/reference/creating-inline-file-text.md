---
description: '詳細情報: インラインファイルテキストの作成'
title: インライン ファイルのテキストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 849273fff4ca0853e4589a38096cbb067c380aae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196855"
---
# <a name="creating-inline-file-text"></a>インライン ファイルのテキストの作成

インラインファイルは、一時的または永続的です。

## <a name="syntax"></a>構文

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>解説

コマンドの後の最初の行に *inlinetext* を指定します。 別の行の先頭に、二重山かっこ (<<) を使用して end をマークします。 このファイルには、区切り角かっこの前にあるすべての *inlinetext* が含まれています。 *Inlinetext* には、マクロの展開と置換を含めることができますが、ディレクティブやメイクファイルのコメントは含めることはできません。 スペース、タブ、および改行文字は、文字どおりに処理されます。

一時ファイルは、セッションの期間中は存在し、他のコマンドで再利用できます。 NMAKE セッションの後にファイルを保持するには、閉じ山かっこの後に **KEEP** を指定します。名前のないファイルは、生成されたファイル名を使用してディスクに保存されます。 一時ファイルには、 **NOKEEP** または nothing を指定します。 **KEEP** と **NOKEEP** では大文字と小文字が区別されません。

## <a name="see-also"></a>関連項目

[メイクファイルのインラインファイル](inline-files-in-a-makefile.md)
