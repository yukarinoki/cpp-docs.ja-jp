---
title: コンパイラの警告 (レベル 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 28d8534dad5fc1b234c180b879ad0645f05cfd65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198615"
---
# <a name="compiler-warning-level-3-c4580"></a>コンパイラの警告 (レベル 3) C4580

[attribute] は非推奨とされます。System::Attribute または Platform::Metadata を基底クラスとして指定してください

[[attribute](../../windows/attributes/attribute.md)] は、ユーザー定義の属性を作成するための推奨される構文ではなくなりました。 詳細については、「 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)」を参照してください。 CLR コードの場合は、`System::Attribute` から属性を派生させます。 Windows ランタイム コードの場合は、`Platform::Metadata` から属性を派生させます。

## <a name="example"></a>例

次の例では、C3454 を生成し、その修正方法を示しています。

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```
