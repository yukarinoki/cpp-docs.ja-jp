---
title: コンパイラの警告 (レベル 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a556fbffad41d04b3eb0ea1acfd5e8739ddd5b68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186804"
---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399

> '*symbol*':/clr: pure を指定してコンパイルした場合、プロセスごとのシンボルを __declspec (dllimport) でマークすることはできません

## <a name="remarks"></a>解説

**/Clr: pure**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

ネイティブイメージまたはネイティブコンストラクトと CLR コンストラクトを含むイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、/clr **: pure**ではなく **/clr**を使用してコンパイルするか、`__declspec(dllimport)`を削除します。

## <a name="example"></a>例

次の例では、C4399 が生成されます。

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
