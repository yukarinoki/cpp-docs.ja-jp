---
title: コンパイラの警告 (レベル 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: fe5306cc7909138fea0159553b53c2adc6a46dc0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498242"
---
# <a name="compiler-warning-level-3-c4240"></a>コンパイラの警告 (レベル 3) C4240

標準の拡張機能を使用します 'アクセス指定子' を 'classname' を 'へのアクセス指定子'、以前のバージョンで定義されましたへのアクセスが定義されました。

ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、入れ子になったクラスにアクセス権を変更することはできません。 既定の Microsoft 拡張 (/Ze) で、この警告をできます。

## <a name="example"></a>例

```
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```