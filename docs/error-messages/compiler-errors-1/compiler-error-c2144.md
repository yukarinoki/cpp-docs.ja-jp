---
title: コンパイラ エラー C2144 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2144
dev_langs:
- C++
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60a6b0a6019ab6ddf1a403d2cbd4f6ef96b2a865
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171149"
---
# <a name="compiler-error-c2144"></a>コンパイラ エラー C2144

> 構文エラー: '*型*'によって先行されなければなりません'*トークン*'

予想コンパイラ*トークン*と見つかる*型*代わりにします。

このエラーは、右中かっこ、右かっこ、またはセミコロンで発生する可能性があります。

C2144 は、空白文字を含む CLR キーワードからマクロを作成しようとするときにも発生することができます。

型の転送しようとしている場合、C2144 する可能性がありますにも参照してください。 参照してください[Type Forwarding (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)詳細についてはします。

## <a name="examples"></a>使用例

次の例では、C2144 を生成し、その修正方法を示しています。

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

次の例では、C2144 を生成し、その修正方法を示しています。

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```