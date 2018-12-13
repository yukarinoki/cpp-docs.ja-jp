---
title: 範囲の読み取り
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: b5c6a6baf43b8786fbd0301e4b89ea856d839606
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604108"
---
# <a name="reading-ranges"></a>範囲の読み取り

**ANSI 4.9.6.2** `fscanf` 関数の % [ 変換でのスキャン リストの最初または最後の文字ではないダッシュ (-) 文字の解釈

次の行

```
fscanf( fileptr, "%[A-Z]", strptr);
```

`strptr` が指す文字列に A から Z の範囲の任意の文字数を読み取ります。

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)