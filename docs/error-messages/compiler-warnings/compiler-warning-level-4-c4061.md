---
description: '詳細情報: コンパイラの警告 (レベル 4) C4061'
title: コンパイラの警告 (レベル 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 9e76fd864e57e6d84ed28b1646e8950186945d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262062"
---
# <a name="compiler-warning-level-4-c4061"></a>コンパイラの警告 (レベル 4) C4061

> 列挙型 '*enumeration*' の switch の列挙子 '*identifier*' は、case ラベルによって明示的に処理されていません

指定された列挙子 *識別子* には、ケースのあるステートメントに関連付けられたハンドラーがありません **`switch`** **`default`** 。 見つからないケースは、監視である場合もあれば、問題にならない場合もあります。 列挙子が既定のケースによって処理されるかどうかによって異なります。 ステートメント内の未使用の列挙子に関する関連する警告につい **`switch`** **`default`** ては、「 [C4062](compiler-warning-level-4-c4062.md)」を参照してください。

既定では、この警告はオフに設定されています。 既定でオフになっている警告を有効にする方法の詳細については、「 [既定でオフになっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4061 が生成されます。不足している列挙子を修正するケースを追加します。

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```

## <a name="see-also"></a>関連項目

[コンパイラの警告 (レベル 4) C4062](compiler-warning-level-4-c4062.md)
