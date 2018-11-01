---
title: bad_alloc クラス
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 1ebb427277c985fdab711d5bd84dcea54898a83b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515610"
---
# <a name="badalloc-class"></a>bad_alloc クラス

このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。

## <a name="syntax"></a>構文

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>Remarks

によって返される値`what`実装で定義された C 文字列します。 このメンバー関数は、いずれも例外をスローしません。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<new>

**名前空間:** std

## <a name="example"></a>例

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>出力例

```Output
bad allocation
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<new>

## <a name="see-also"></a>関連項目

[exception クラス](../standard-library/exception-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
