---
title: コンパイラ エラー C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: bed23b7d9117d1d1acad80f4f3d81e8b0b9d0252
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366421"
---
# <a name="compiler-error-c2944"></a>コンパイラ エラー C2944

'class': type-class-id が、テンプレートの値引数として再定義されています

テンプレートの値引数として、シンボルの代わりにジェネリックまたはテンプレート クラスを使うことはできません。

次の例では C2944 が生成されます。

```
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

ジェネリックを使用する場合も C2944 が発生する場合があります。

```
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```