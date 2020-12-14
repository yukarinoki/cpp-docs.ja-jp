---
description: '詳細情報: コンパイラの警告 (レベル 4) C4057'
title: コンパイラの警告 (レベル 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 0b5da5c4768f4101b7b1780b5d0518ed723c5225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262088"
---
# <a name="compiler-warning-level-4-c4057"></a>コンパイラの警告 (レベル 4) C4057

'operator' : 'identifier1' と 'identifier2' で間接参照している基本型が微妙に異なっています

2 つのポインター式が参照する基本型が異なります。 式は変換されずに使用されます。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. signed 型と unsigned 型が混在しています。

1. **`short`** と **`long`** 型の混合。
