---
title: コンパイラ エラー C2842 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20967ab4cd047f62a5cf692c91fec90148b4f470
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118818"
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
