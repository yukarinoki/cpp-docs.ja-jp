---
description: '詳細情報: コンパイラの警告 (レベル 4) C4201'
title: コンパイラの警告 (レベル 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: 739e09750f8f051ee0fd380fbb25858e620c70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206722"
---
# <a name="compiler-warning-level-4-c4201"></a>コンパイラの警告 (レベル 4) C4201

非標準の拡張機能が使用されています: 無名の構造体/共用体

[Microsoft extensions (/Ze)] では、宣言子が別の構造体または共用体のメンバーとして指定されていない構造体を指定できます。 これらの構造体は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) でエラーを生成します。

## <a name="example"></a>例

```cpp
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```
