---
description: 詳細については、「NMAKE の致命的なエラー U1070」を参照してください。
title: NMAKE の致命的なエラー U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: a3d0ee448062fec8a024501b0c08d5f0466d974b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283525"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE の致命的なエラー U1070

マクロ定義 ' macroname ' 内の循環

指定されたマクロ定義には、指定されたマクロを含む定義を持つマクロが含まれていました。 循環マクロ定義が無効です。

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
