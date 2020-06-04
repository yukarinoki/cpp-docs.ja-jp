---
title: コンパイラの警告 (レベル 1) C4621
ms.date: 11/04/2016
f1_keywords:
- C4621
helpviewer_keywords:
- C4621
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
ms.openlocfilehash: a48934fd097f9039988db32511ca87cbd66b22d2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199753"
---
# <a name="compiler-warning-level-1-c4621"></a>コンパイラの警告 (レベル 1) C4621

型 ' type ' に対して後置形式でない ' operator--' が見つかりました。プレフィックス形式を使用します

指定された型に後置デクリメント演算子が定義されていませんでした。 コンパイラは、オーバーロードされた前置演算子を使用します。

この警告は、後置 `--` 演算子を定義することで回避できます。 次に示すように、`--` 演算子の2つの引数を持つバージョンを作成します。

```cpp
// C4621.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator--()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator--(int)
   // {
   //    A tmp = *this;
   //    m_nData -= 1;
   //    return tmp;
   // }

private:
   int m_nData;
};

int main()
{
   A a(10);
   --a;
   a--;   // C4621
}
```
