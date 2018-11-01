---
title: コンパイラ エラー C2244
ms.date: 11/04/2016
f1_keywords:
- C2244
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
ms.openlocfilehash: 7cfa0cd7ff4290ca5f07fb712bbcac7dabf55f29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615203"
---
# <a name="compiler-error-c2244"></a>コンパイラ エラー C2244

'identifier': 関数の定義を既存の宣言と一致しません

単項 + 演算子の異常の使用は、かっこがない関数呼び出しの前に使用されました。

このエラーは、C++ プロジェクトでのみ発生します。

次の例では、C2244 が生成されます。

```
// C2244.cpp
int func(char) {
   return 0;
}

int func(int) {
   return 0;
}

int main() {
   +func;   // C2244
}
```

C2244 は、クラス テンプレートのメンバー関数に、無効な関数のシグネチャを使用する場合にも発生します。

```
// C2244b.cpp
// compile with: /c
template<class T>
class XYZ {
   void func(T t);
};

template<class T>
void XYZ<T>::func(int i) {}   // C2244 wrong function signature
// try the following line instead
// void XYZ<T>::func(T t) {}
```

C2244 は、メンバー関数テンプレートに、無効な関数のシグネチャを使用する場合にも発生します。

```
// C2244c.cpp
// compile with: /c
class ABC {
   template<class T>
   void func(int i, T t);
};

template<class T>
void ABC::func(int i) {}   // C2244 wrong signature
// try the following line instead
// void ABC::func(int i, T t) {}
```

関数テンプレートの部分的な特化することはできません。

```
// C2244d.cpp
template<class T, class U>
class QRS {
   void func(T t, U u);
};

template<class T>
void QRS<T,int>::func(T t, int u) {}   // C2244
```