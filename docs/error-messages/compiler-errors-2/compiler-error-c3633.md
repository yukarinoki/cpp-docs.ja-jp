---
title: コンパイラ エラー C3633 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaa4712fb571d56166204655aff95153ac328ce6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078271"
---
# <a name="compiler-error-c3633"></a>コンパイラ エラー C3633

管理対象の 'type' のメンバーとして 'member' を定義することはできません。

CLR 参照クラスのデータ メンバーは、pod 型以外の C++ 型のすることはできません。  CLR 型でポッドのネイティブな型をインスタンス化することができますのみ。  たとえば、POD 型では、コピー コンス トラクターまたは代入演算子を含めることはできません。

## <a name="example"></a>例

次の例では、C3633 が生成されます。

```
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
