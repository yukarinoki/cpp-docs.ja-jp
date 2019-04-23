---
title: コンパイラ エラー C3492
ms.date: 11/04/2016
f1_keywords:
- C3492
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
ms.openlocfilehash: facd8c78e775945924d77b09f9dc754bdc301ddd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038820"
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