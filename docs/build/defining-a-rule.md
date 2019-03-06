---
title: 規則の定義
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 7031f56d82fcaf557388c7600d493ebda48add1a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416931"
---
# <a name="defining-a-rule"></a>規則の定義

*Fromext*依存のファイルの拡張機能を表すと*toext*ターゲット ファイルの拡張子を表します。

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Remarks

拡張は、大文字小文字が区別されていません。 表すマクロを呼び出すことができる*fromext*と*toext*; マクロは、プリプロセス時に展開されます。 上記ピリオド (.) *fromext*行の先頭に置く必要があります。 コロン (:) は、スペースまたはタブの 0 個以上続きます。 これは、スペースまたはタブ、コマンドを指定するにはセミコロン (;)、番号記号 (#)、コメントを指定して、または改行文字によってのみ実行できます。 その他の空白は許可されません。 記述ブロックのように、コマンドが指定されます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[規則の検索パス](../build/search-paths-in-rules.md)

## <a name="see-also"></a>関連項目

[推論規則](../build/inference-rules.md)
