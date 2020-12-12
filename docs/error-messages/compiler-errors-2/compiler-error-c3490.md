---
description: 詳細については、「コンパイラエラー C3490」を参照してください。
title: コンパイラ エラー C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 03896872fd0c683e3011aa7edbacb6a0a01ceaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113364"
---
# <a name="compiler-error-c3490"></a>コンパイラ エラー C3490

'var' は const オブジェクトを通じてアクセスされているため変更できません

メソッドで宣言されているラムダ式は、 **`const`** 変更できないメンバーデータを変更することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- **`const`** メソッド宣言から修飾子を削除します。

## <a name="examples"></a>例

次の例では、メソッドでメンバー変数を変更するため、C3490 が生成され `_i` **`const`** ます。

```cpp
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

次の例では、メソッド宣言から修飾子を削除することによって、C3490 を解決し **`const`** ます。

```cpp
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
