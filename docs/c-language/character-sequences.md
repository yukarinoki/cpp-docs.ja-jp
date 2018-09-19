---
title: 文字シーケンス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cf3b52b8a4e76062d06b0b9ca3d4535b79595c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061514"
---
# <a name="character-sequences"></a>文字シーケンス

**ANSI 3.8.2** ソース ファイルの文字シーケンスのマッピング

プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。

したがって、インクルード ファイルのパスを指定するには、1 つの円記号 (バックスラッシュ) のみを使用します。

```
#include "path1\path2\myfile"
```

ソース コード内では、次のように、2 つの円記号 (バックスラッシュ) が必要です。

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>参照

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)