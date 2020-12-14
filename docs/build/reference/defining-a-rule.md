---
description: '詳細情報: ルールの定義'
title: 規則の定義
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 89a5db90162ede02743aa469ac4f9e3d75c5e147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201678"
---
# <a name="defining-a-rule"></a>規則の定義

*Fromext* は、依存ファイルの拡張子を表し、 *toext* はターゲットファイルの拡張子を表します。

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>解説

拡張機能では大文字と小文字が区別されません。 *Fromext* と *toext* を表すマクロを呼び出すことができます。マクロは、前処理中に展開されます。 *Fromext* の前のピリオド (.) は、行の先頭に記述する必要があります。 コロン (:)の前に0個以上の空白またはタブがあります。 この文字の後には、スペースまたはタブ、セミコロン (;)コマンドを指定するには、シャープ記号 (#) を指定してコメントまたは改行文字を指定します。 その他のスペースは許可されません。 コマンドは、説明ブロックでとして指定されます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[規則の検索パス](search-paths-in-rules.md)

## <a name="see-also"></a>関連項目

[推論規則](inference-rules.md)
