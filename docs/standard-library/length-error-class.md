---
title: length_error クラス
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::length_error
helpviewer_keywords:
- length_error class
ms.assetid: d53c46c5-4626-400d-bd76-bf3e1e0f64ae
ms.openlocfilehash: 740ae69948a8f1975872f223ba51fb669121a891
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520889"
---
# <a name="length_error-class"></a>length_error クラス

このクラスは、生成を試みたオブジェクトが長すぎて指定できないことを通知するためにスローされる例外すべてに対する基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class length_error : public logic_error {
public:
    explicit length_error(const string& message);

    explicit length_error(const char *message);

};
```

## <a name="remarks"></a>Remarks

によって返される値 `what()` は、のコピーです `message.data()` 。 詳細については、[`what`](../standard-library/exception-class.md) および [`data`](../standard-library/basic-string-class.md#data) を参照してください。

## <a name="example"></a>例

```cpp
// length_error.cpp
// compile with: /EHsc /GR /MDd
#include <vector>
#include <iostream>

using namespace std;

template<class  T>
class stingyallocator : public allocator< T>
{
public:
   template <class U>
      struct rebind { typedef stingyallocator<U> other; };
   _SIZT max_size( ) const
   {
         return 10;
   };

};

int main( )
{
   try
   {
      vector<int, stingyallocator< int > > myv;
      for ( int i = 0; i < 11; i++ ) myv.push_back( i );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught vector<T> too long
Type class std::length_error
*/
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<stdexcept>

**名前空間:** std

## <a name="see-also"></a>関連項目

[logic_error クラス](../standard-library/logic-error-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
