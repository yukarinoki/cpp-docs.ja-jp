---
description: '詳細情報: コンパイラの警告 (レベル 3) C4240'
title: コンパイラの警告 (レベル 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 95e704b6ad91ff77c4def0b4fa1fe8fad002e5ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344199"
---
# <a name="compiler-warning-level-3-c4240"></a>コンパイラの警告 (レベル 3) C4240

非標準の拡張機能が使用されています: ' classname ' へのアクセスは ' アクセス指定子 ' として定義されましたが、以前は ' access 指定子 ' として定義されました

ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では、入れ子になったクラスへのアクセスを変更することはできません。 既定の Microsoft 拡張機能 (/Ze) では、この警告が表示されます。

## <a name="example"></a>例

```cpp
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
