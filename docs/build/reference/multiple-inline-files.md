---
description: '詳細情報: 複数のインラインファイル'
title: 複数のインライン ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: d739591910007f69eca5d4834f6943ae0a0082ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190602"
---
# <a name="multiple-inline-files"></a>複数のインライン ファイル

コマンドでは、複数のインラインファイルを作成できます。

## <a name="syntax"></a>構文

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>解説

各ファイルに対して、1行以上のインラインテキストの後に区切り記号を含む終了行を指定します。 最初のファイルの区切り行の後の行で、2番目のファイルのテキストを開始します。

## <a name="see-also"></a>関連項目

[メイクファイルのインラインファイル](inline-files-in-a-makefile.md)
