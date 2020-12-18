---
description: '詳細情報: 範囲の読み取り'
title: 範囲の読み取り
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: afb1ff0f25360de7c47663279bf6f54dd7ca6a48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309122"
---
# <a name="reading-ranges"></a>範囲の読み取り

**ANSI 4.9.6.2**`fscanf` 関数の % [ 変換でのスキャン リストの最初または最後の文字ではないダッシュ (-) 文字の解釈

次の行

```
fscanf( fileptr, "%[A-Z]", strptr);
```

`strptr` が指す文字列に A から Z の範囲の任意の文字数を読み取ります。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)
