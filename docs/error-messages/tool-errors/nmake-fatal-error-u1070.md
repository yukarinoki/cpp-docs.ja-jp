---
title: NMAKE の致命的なエラー U1070 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb462e5c3c7e497cde55151bf92c62ffb2afcd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087020"
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