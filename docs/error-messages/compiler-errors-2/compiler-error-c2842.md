---
description: 詳細については、「コンパイラエラー C2842」を参照してください。
title: コンパイラ エラー C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: f086c6c5fcfa451f320d96470615e4f5f4d5674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119984"
---
# <a name="compiler-error-c2842"></a>コンパイラ エラー C2842

> '*class*': マネージ型または WinRT 型で、独自の ' operator new ' または ' operator delete ' を定義することはできません

## <a name="remarks"></a>解説

独自の **operator new** または **operator delete** を定義して、ネイティブヒープでのメモリ割り当てを管理できます。 ただし、これらの演算子はマネージド ヒープでのみ割り当てられるため、参照クラスでは定義できません。

詳細については、「 [ユーザー定義の演算子 (C++/cli)](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C2842 が生成されます。

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
