---
description: '詳細情報: コンパイラの警告 (レベル 1) C4399'
title: コンパイラの警告 (レベル 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a1d0fab62d13c08fb2117279d9173786c65d846f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311137"
---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399

> '*symbol*':/clr: pure を指定してコンパイルした場合、プロセスごとのシンボルを __declspec (dllimport) でマークすることはできません

## <a name="remarks"></a>解説

**/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

ネイティブイメージまたはネイティブコンストラクトと CLR コンストラクトを含むイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、 **/clr** ( **/clr: pure** ではなく) を使用してコンパイルするか、または削除 `__declspec(dllimport)` します。

## <a name="example"></a>例

次の例では、C4399 が生成されます。

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
