---
title: NMAKE の致命的なエラー U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 35bea47f6626dfe283a537d3d96340921c37f3f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484215"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE の致命的なエラー U1070

マクロ定義 'macroname' に循環定義

特定のマクロ定義には、その定義には、特定のマクロが含まれているマクロが含まれています。 循環マクロ定義が無効です。

## <a name="example"></a>例

次のマクロ定義

```
ONE=$(TWO)
TWO=$(ONE)
```

次のエラーが発生します。

```
cycle in macro definition 'TWO'
```