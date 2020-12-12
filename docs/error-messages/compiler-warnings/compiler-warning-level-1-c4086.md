---
description: '詳細情報: コンパイラの警告 (レベル 1) C4086'
title: コンパイラの警告 (レベル 1) C4086
ms.date: 11/04/2016
f1_keywords:
- C4086
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
ms.openlocfilehash: e2bb38d781a18b98a386e17ccdb347be9fe0f0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278117"
---
# <a name="compiler-warning-level-1-c4086"></a>コンパイラの警告 (レベル 1) C4086

プラグマに '1'、'2'、'4'、'8'、'16' のいずれかのパラメーターが必要です。

プラグマのパラメーターに必要な値 (1、2、4、8、または 16) がありません。

## <a name="example"></a>例

```cpp
// C4086.cpp
// compile with: /W1 /LD
#pragma pack( 3 ) // C4086
```
