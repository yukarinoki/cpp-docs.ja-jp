---
title: 範囲の読み取り | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76530dfdac917dfbde50bc3fb1b17a3c31178729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030243"
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