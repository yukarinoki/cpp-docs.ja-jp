---
title: コンパイラの警告 (レベル 1) C4930 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4930
dev_langs:
- C++
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33c202cc6f062ac13bef3a73e4509e4ba870e2d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090192"
---
# <a name="compiler-warning-level-1-c4930"></a>コンパイラの警告 (レベル 1) C4930

'プロトタイプ': プロトタイプ宣言された関数が呼び出されません (でした変数の定義が対象としていますか?)

未使用の関数プロトタイプが検出されました。 プロトタイプは、変数の宣言として用意されていますが場合、は、開く/閉じるかっこを削除します。

次の例では、C4930 が生成されます。

```
// C4930.cpp
// compile with: /W1
class Lock {
public:
   int i;
};

void f() {
   Lock theLock();   // C4930
   // try the following line instead
   // Lock theLock;
}

int main() {
}
```

C4930 は、コンパイラが関数のプロトタイプ宣言と関数の呼び出しの間で区別できないときにも発生します。

次の例では、C4930 が生成されます。

```
// C4930b.cpp
// compile with: /EHsc /W1

class BooleanException
{
   bool _result;

public:
   BooleanException(bool result)
      : _result(result)
   {
   }

   bool GetResult() const
   {
      return _result;
   }
};

template<class T = BooleanException>
class IfFailedThrow
{
public:
   IfFailedThrow(bool result)
   {
      if (!result)
      {
         throw T(result);
      }
   }
};

class MyClass
{
public:
   bool MyFunc()
   {
      try
      {
         IfFailedThrow<>(MyMethod()); // C4930

         // try one of the following lines instead
         // IfFailedThrow<> ift(MyMethod());
         // IfFailedThrow<>(this->MyMethod());
         // IfFailedThrow<>((*this).MyMethod());

         return true;
      }
      catch (BooleanException e)
      {
         return e.GetResult();
      }
   }

private:
   bool MyMethod()
   {
      return true;
   }
};

int main()
{
   MyClass myClass;
   myClass.MyFunc();
}
```

上記のサンプルでは、0 個の引数を受け取るメソッドの結果は、名前のないローカル クラス変数のコンス トラクターに引数として渡されます。 呼び出しは、ローカル変数を付けたか、またはオブジェクト インスタンスを適切なメンバーへのポインター演算子と共にメソッド呼び出しを付けることが明確に区別できます。