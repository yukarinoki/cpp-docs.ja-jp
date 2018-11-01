---
title: コンパイラ エラー C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: 53dd22368aee5e0de9eca1349eb4d7dd3ed1c570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485008"
---
# <a name="compiler-error-c3492"></a>コンパイラ エラー C3492

'var': 匿名共用体のメンバーをキャプチャすることはできません

無名の共用体のメンバーをキャプチャすることはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 共用体に名前を付け、ラムダ式のキャプチャの一覧に、完全な共用体の構造体を渡します。

## <a name="example"></a>例

次の例では、匿名共用体のメンバーをキャプチャするために C3492 が生成されます。

```
// C3492a.cpp

int main()
{
   union
   {
      char ch;
      int x;
   };

   ch = 'y';
   [&x](char ch) { x = ch; }(ch); // C3492
}
```

## <a name="example"></a>例

次の例では、共用体に名前を付け、ラムダ式のキャプチャの一覧に完全な共用体の構造を渡すことによって、C3492 が解決されます。

```
// C3492b.cpp

int main()
{
   union
   {
      char ch;
      int x;
   } u;

   u.ch = 'y';
   [&u](char ch) { u.x = ch; }(u.ch);
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)