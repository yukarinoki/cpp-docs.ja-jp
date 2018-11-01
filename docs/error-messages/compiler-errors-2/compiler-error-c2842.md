---
title: コンパイラ エラー C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: 2ec39768a88da049c6a31ca2a9de226e25479c99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571471"
---
# <a name="compiler-error-c2842"></a>コンパイラ エラー C2842

'class' : マネージド型または WinRT 型はそれ自体の 'operator new' または 'operator delete' を定義できません

独自に定義することができます * * new 演算子または**delete 演算子**ネイティブ ヒープにメモリの割り当てを管理します。 ただし、これらの演算子はマネージド ヒープでのみ割り当てられるため、参照クラスでは定義できません。

詳細については、次を参照してください。[ユーザー定義演算子 (C +/cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C2842 が生成されます。

```
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
