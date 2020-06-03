---
title: コンパイラの警告 (レベル 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 45d2db56a7b0fc871de60743954012faf0f5c366
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185387"
---
# <a name="compiler-warning-level-4-c4057"></a>コンパイラの警告 (レベル 4) C4057

'operator' : 'identifier1' と 'identifier2' で間接参照している基本型が微妙に異なっています

2 つのポインター式が参照する基本型が異なります。 式は変換されずに使用されます。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. signed 型と unsigned 型が混在しています。

1. **short** 型と **long** 型が混在しています。
