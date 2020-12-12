---
description: '詳細情報: コンパイラの警告 (レベル 1) C4176'
title: コンパイラの警告 (レベル 1) C4176
ms.date: 11/04/2016
f1_keywords:
- C4176
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
ms.openlocfilehash: 9ba6e0ec6dff72d875aecc74e51d6f9a7e1c05e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266898"
---
# <a name="compiler-warning-level-1-c4176"></a>コンパイラの警告 (レベル 1) C4176

'subcomponent': #pragma コンポーネント ブラウザーで認識できない成分を指定しました。

**component** プラグマに、無効なサブコンポーネントが含まれています。 特定の名前への参照を除外するには、名前の前に **references** オプションを使用する必要があります。

## <a name="example"></a>例

```cpp
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```
