---
description: '詳細情報: コンパイラの警告 (レベル 1) C4326'
title: コンパイラの警告 (レベル 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d7c82d7a0157b53e60281bbe7c45a38cc765a73d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340047"
---
# <a name="compiler-warning-level-1-c4326"></a>コンパイラの警告 (レベル 1) C4326

> '*function*' の戻り値の型 *は ' type1 ' で* はなく '*type1*' でなければなりません

## <a name="remarks"></a>解説

関数が *type1* 以外の型を返しました。 たとえば、 [/za](../../build/reference/za-ze-disable-language-extensions.md)を使用すると、 **main** はを返しませんでした **`int`** 。

## <a name="example"></a>例

次の例では、C4326 を生成し、その修正方法を示しています。

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```
