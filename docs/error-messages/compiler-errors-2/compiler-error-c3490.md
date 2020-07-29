---
title: コンパイラ エラー C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: ea7341b9c587a764c7366fa7b7c89e4fc67bc7d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230858"
---
# <a name="compiler-error-c3490"></a>コンパイラ エラー C3490

'var' は const オブジェクトを通じてアクセスされているため変更できません

メソッドで宣言されているラムダ式は、 **`const`** 変更できないメンバーデータを変更することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- **`const`** メソッド宣言から修飾子を削除します。

## <a name="example"></a>例

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

## <a name="example"></a>例

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
