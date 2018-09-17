---
title: インライン ファイルのテキストを作成する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce0a345c6c2f48d3d5c2e6fb9d9cfc2a5c03e4ed
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720918"
---
# <a name="creating-inline-file-text"></a>インライン ファイルのテキストの作成

インライン ファイルは、一時的または永続的です。

## <a name="syntax"></a>構文

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Remarks

指定*inlinetext*コマンドの後に最初の行にします。 二重山かっこと終わりをマーク (<<) を別の行の先頭にします。 ファイルがすべて含まれています*inlinetext*区切り記号の角かっこの前にします。 *Inlinetext*マクロの展開との置換がしないディレクティブまたはメイクファイルのコメントを持つことができます。 スペース、タブ、および改行文字リテラルに扱われます。

一時ファイルは、セッションの間存在し、その他のコマンドで再利用することができます。 指定**保持**NMAKE セッション後にファイルを保持する閉じる山かっこの後に、名前のないファイルが生成されたファイル名でディスクに保存されます。 指定**NOKEEP**または一時ファイルのものがありません。 **保持**と**NOKEEP**小文字は区別されません。

## <a name="see-also"></a>関連項目

[メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)